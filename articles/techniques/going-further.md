---
title: 'Q # 技術-進一步探討 |Microsoft Docs'
description: 'Q # 技術-進一步'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: c079364f8808304e0132fa2a4226cd6400e81339
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863141"
---
# <a name="going-further"></a>更進一步 #

既然您已瞭解如何在 Q # 中撰寫有趣的配量程式，本節將進一步介紹一些更先進的主題，以供未來使用。


## <a name="generic-operations-and-functions"></a>一般作業和函數 ##

> [!TIP]
> 本節假設您對[中C#的泛型](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics) [、 F#中的泛型、](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/) [ C++範本](https://docs.microsoft.com/cpp/cpp/templates-cpp)或類似的方法，對其他語言的元人員有基本的熟悉程度。

我們可能會想要定義的許多函式和作業實際上並不會依賴其輸入的類型，而只會透過一些其他函式或運算，隱含地使用其類型。
例如，請考慮許多功能性語言通用的*地圖*概念;假設函式 $f （x） $ 和值 $\{的集合 x_1，x_2，\dots ..，x_n\}$，map 會傳回新的集合 $\{f （x_1），f （x_2），\dots ..，f （x_n）\}$。
若要在 Q # 中執行此功能，我們可以利用該函式是第一個類別。
讓我們寫出 `Map`的快速範例，使用★作為預留位置，同時瞭解我們所需的類型。

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

請注意，無論我們在什麼實際的型別中，此函式看起來都很相似。
例如，從整數到 Paulis 的對應，與從浮點數到字串的對應大致相同：

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

在原則上，我們可以針對我們所遇到的每一對類型撰寫 `Map` 版本，但這會造成一些問題。
比方說，如果我們在 `Map`中發現錯誤，則必須確保在所有 `Map`版本上一致地套用修正程式。
此外，如果我們要建立新的元組或 UDT，則現在也必須建立新的 `Map` 來與新的型別搭配使用。
雖然這是少數這類函式的方便追蹤，但我們會收集與 `Map`相同形式的多個函式，而引入新類型的成本會以相當短的順序過長為大。

不過，大部分的困難之處在于，我們並未提供編譯器所需的資訊來辨識不同版本的 `Map` 相關聯的方式。
實際上，我們希望編譯器將 `Map` 視為某種數學函式，從 Q # 型別*到 q* # 函數。
這種概念的正規化方式是讓函式和作業具有*型別參數*，以及它們的一般元組參數。
在上述範例中，我們想要將 `Map` 視為 `Int, Pauli` 第一個案例中的型別參數，並在第二個案例中 `Double, String`。
在大部分的情況下，這些類型參數可以用來當做一般類型使用：我們會使用類型參數的值來建立陣列和元組、呼叫函數和作業，以及指派給一般或可變變數。

> [!NOTE]
> 間接相依性最極端的情況，就是 qubits，其中 Q # 程式無法直接依賴 `Qubit` 類型的結構，但**必須**將這類類型傳遞給其他作業和函式。

回到上述範例，我們可以看到我們需要 `Map` 具有型別參數，一個用來表示 `fn` 的輸入，另一個則代表 `fn`的輸出。
在 Q # 中，這是藉由在其宣告中的函式或作業名稱後面加上角括弧（也就是 `<>`，而不是 brakets $ \braket{}$！）來撰寫，並列出每個類型參數。
每個型別參數的名稱都必須以 tick `'`開頭，表示它是型別參數，而不是一般型別（也稱為*具體*型別）。
針對 `Map`，我們會撰寫：

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

請注意，`Map<'Input, 'Output>` 的定義看起來非常類似于之前寫出的版本。
唯一的差別在於，我們明確通知編譯器，`Map` 不會直接相依于 `'Input` 和 `'Output`，但可透過 `fn`間接使用來處理任何兩種類型。
一旦以這種方式定義 `Map<'Input, 'Output>` 之後，就可以像一般函式一樣呼叫它：

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> 撰寫泛型函式和作業是一個位置，其中「元組元組輸出」是一種非常有用的方法，可以思考問 # 函式和作業。
> 由於每個函式都只接受一個輸入，而且只會傳回一個輸出，因此類型的輸入 `'T -> 'U` 會符合*任何*Q # 函數。
> 同樣地，任何作業都可以傳遞至 `'T => 'U`類型的輸入。

作為第二個範例，請考慮撰寫會傳回兩個其他函式之組合的函式的挑戰：

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

在這裡，我們必須確切指定 `A`、`B`和 `C` 的內容，因此會嚴重限制新的 `Compose` 函數的公用程式。
畢竟，`Compose` 只取決於 `A`、`B`，以及透過 `innerFn`*和 `outerFn`的 `C`。*
或者，我們可以將型別參數新增至 `Compose`，表示它適用于*任何*`A`、`B`和 `C`，只要這些參數符合 `innerFn` 和 `outerFn`所預期的參數即可：

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Q # 標準程式庫提供了這類類型參數化作業和函式的範圍，讓您更容易表達更高順序的控制流程。
這些會在[問答 # 標準程式庫指南](xref:microsoft.quantum.libraries.standard.intro)中進一步討論。

## <a name="borrowing-qubits"></a>借用 Qubits ##

「借款」機制可讓您配置 qubits，在計算期間用來做為臨時空間。 這些 qubits 通常不是處於乾淨狀態，也就是說，它們不一定會在已知狀態中初始化，例如 $ \ket{0}$。 其中一個人也說「中途」 qubits，因為其狀態不明，甚至可以與量子電腦記憶體的其他部分光子。 在已變更 qubits 的已知使用案例中，是多個受控制 CNOT-CONTAINS 閘道的實作為，只需要極少的 qubits 和 incrementers。

在 canon 中，有使用 `borrowing` 關鍵字的範例，例如，`MultiControlledXBorrow` 定義的函數。
如果 `controls` 代表應該加入 `X` 作業中的控制項 qubits，則這個執行會新增 `Length(controls)-2` 許多中途 ancillas 的整體。

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

請注意，`With` 結合---的廣泛使用，其格式適用于支援 adjoint 的作業，也就是在此範例中進行 `WithA`---，這是很好的程式設計風格，因為將控制項加入至包含 `With` 的結構只會將控制項傳播至內部作業。 此外，請注意，除了作業的 `body` 之外，也會明確提供作業的 `controlled` 主體的執行，而不是使用 `controlled auto` 的語句。 這是因為我們從線路的結構得知如何輕鬆加入進一步的控制項，相較于將控制項新增至 `body`中的每個個別閘道。 

將此程式碼與另一個 canon 函式進行比較有其意義 `MultiControlledXClean` 這種方式可達到相同的目標來執行乘法控制的 `X` 作業，不過，它會使用 `using` 機制的幾個乾淨 qubits。 
