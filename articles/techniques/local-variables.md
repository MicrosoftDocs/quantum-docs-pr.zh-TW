---
title: '區域變數-Q # 技術 |Microsoft Docs'
description: '區域變數-Q # 技術'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: 8b1de5c096210fb36a81c127a8bbbe1b39522741
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820176"
---
# <a name="local-variables"></a>區域變數 #

您可以使用 `let` 關鍵字，將 Q # 中任何類型的值指派給變數，以便在作業或函數內重複使用。
例如：

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

這會將特定的 Pauli 運算子陣列指派給名為 `measurementOperator`的變數。

> [!TIP]
> 請注意，我們不需要明確指定新變數的類型，因為 `let` 語句右邊的運算式是明確的，而且該類型是由編譯器推斷。 

Q # 中的變數是*不可變*的，這表示一旦以這種方式定義變數之後，就無法再以任何方式進行變更。
這可提供數個有用的優化，包括優化要重新排序之變數的傳統邏輯，以套用作業的 `Adjoint` 變體。

使用上述 `let` 系結所定義的變數是特定範圍的區域，例如作業的主體或 `for` 迴圈的內容。


## <a name="mutability"></a>可變動性 ##

做為使用 `let`建立變數的替代方法，`mutable` 關鍵字會建立一開始使用 `set` 關鍵字來建立的特殊可變變數。

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

Q # 中的所有類型（包括陣列）都會遵循值的語義。 特別是，不可能更新陣列專案。 若要修改現有的陣列，您必須利用與中F#記錄相同的複製和更新機制。 針對[`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)中提供的陣列使用程式庫工具，我們可以輕鬆地定義函式，以傳回 Paulis 的陣列，其中 index `i` 的會採用指定的值，而所有其他專案都是身分識別： 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

在討論問 # 語句和運算式時，我們將詳細說明如何使用陣列。 

Q # 中的可變動性是套用至*符號*（而不是類型或值）的概念。 具體而言，它沒有隱含或明確的類型系統中的標記法，而且系結是否可變動（如 `mutable` 關鍵字所指示）或不可變（如 `let`所表示）不會變更系結變數的類型。 這會提供一個重要的方式來隔離特定函式和作業中的可變動性。
特別的是，即使使用可變動變數之作業的 adjoint 特製化無法自動產生，當作業呼叫使用可變動性的函式時，自動產生功能也會正常運作。
基於這個理由，最好的做法是讓使用可變動性的函式和作業盡可能精簡，讓其餘的量副程式可以使用一般的不可變變數來撰寫。


## <a name="deconstruction"></a>解構 ##

除了指派單一變數之外，`let` 和 `mutable` 關鍵字，或事實上任何其他系結結構，也允許將[元組類型](xref:microsoft.quantum.language.type-model#tuple-types)的內容解壓縮。
這個表單的指派是用來*解構*該元組的元素。
比方說，如果我們以元組為 Hamiltonian 中的詞彙建立模型，則可以使用解構來存取我們在該詞彙下需要模擬的不同資料：

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


