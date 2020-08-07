---
title: Q#操作
description: 的基本概念Q#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4f4a75cdaaa070fd763d7f75429b7c39357d25a5
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869642"
---
# <a name="no-locq-basics"></a>Q#操作

本文提供的基本組建組塊簡介 Q# 。

如需瞭解其適用 Q# 于作為配量開發工具組的基本元件，以及其所在位置的總覽，請參閱[什麼是 Q# ？](xref:microsoft.quantum.overview.q-sharp)。 

## <a name="what-is-a-quantum-program"></a>什麼是量副程式？

從技術觀點來看，配量程式是一組特定的傳統副程式，在被呼叫時，會在量子系統上執行某些作業。
該觀點的重要結果是，程式不 Q# 會直接建立 qubits 本身的模型，而是描述傳統方式控制的電腦如何與這些 qubits 互動。
根據設計，不 Q# 會直接定義配量狀態或其他的量子機制屬性。
例如，請考慮「量子計算概念指南」中所討論的狀態 $ \ket{+} = \left ( \ket {0} + \ket {1} \right) /\sqrt {2} $。 [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)
若要在中準備此狀態 Q# ，請從 qubits 以 $ \ket $ 狀態初始化的事實開始， {0} 然後按 $ \ket{+} = H\ket {0} $，其中 $H $ 是由[ `H` 作業所](xref:microsoft.quantum.intrinsic.h)執行的[Hadamard 轉換](xref:microsoft.quantum.glossary#hadamard)。 初始化和轉換 qubit 的基本程式碼，如下所示 Q# ：

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
如需有關*初始化或配置*qubits 的詳細資訊，請參閱[使用 qubits](xref:microsoft.quantum.guide.qubits)。

## <a name="quantum-states-in-no-locq"></a>中的量子狀態Q#

重要的是，先前的程式並不會明確參考內的狀態，而是會 Q# 描述程式如何*轉換*狀態。
使用這種方法，您可以完全找出每一部目的電腦*上的*量子狀態為何，這可能會有不同的解讀，視電腦而定。 

Q#程式無法 introspect 至 qubit 的狀態。
相反地，程式可以呼叫作業（例如） [`Measure`](xref:microsoft.quantum.intrinsic.measure) 以從 qubit 中學習資訊，以及呼叫和之類的作業 [`X`](xref:microsoft.quantum.intrinsic.x) 來處理 [`H`](xref:microsoft.quantum.intrinsic.h) qubit 的狀態。
這些作業實際*執行*的動作，只會由用來執行特定程式的目的電腦進行具體處理 Q# 。
例如，如果在我們的[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器上執行程式，模擬器會對模擬的量子系統執行對應的數學運算。
但在未來，當目的機器是真實的量子電腦時，在中呼叫這類作業會 Q# 引導量子電腦在*實際*的量子系統上執行對應的*實際*作業，例如，精確地計時雷射脈衝) 。

程式會依照 Q# 目的電腦的定義來 recombines 這些作業，以建立更高層級的新作業來表示量子計算。
如此一來， Q# 您就可以輕鬆地表達基礎配量和混合式量子–傳統演算法的邏輯，同時也會與目的機器或模擬器的結構有關。

## <a name="no-locq-operations-and-functions"></a>Q#作業和函式

具體而言， Q# 套裝程式含*作業*、函*functions*式和任何使用者定義類型。 

作業是用來描述量子系統的轉換，而且是最基本的程式建立組塊 Q# 。 在中定義的每個 Q# 作業都會呼叫任何數目的其他作業。

相對於作業，函數是用來描述純粹具*決定性*的傳統行為，而且除了計算傳統值以外，也不會有任何影響。 例如，假設您想要測量程式結尾的 qubits，並將量測結果新增至陣列。
在此情況下， `Measure` 是指示目的電腦對 (real 或模擬) qubits 執行測量的*運算*。 同時 *，函*式會處理將傳回的結果新增至陣列的傳統程式。

作業和函數統稱為*callables*。 其基礎結構和行為會在中引進，並詳述于[中 Q# 的作業和功能](xref:microsoft.quantum.guide.operationsfunctions)。


## <a name="no-locq-syntax-overview"></a>Q#語法總覽

語言的語法描述形成語法正確程式的不同符號組合。
在中 Q# ，語法元素會分類成三個不同的群組：類型、運算式和語句。

### <a name="types"></a>型別
Q#是強型別語言，因此謹慎使用型別可以協助編譯器在編譯時期提供有關程式的強式保證 Q# 。
除了標準和量子特定的內建基本類型（例如、、 `Int` 和）之外， `Bool` `Qubit` 也 `Result` Q# 提供使用者定義類型的支援。

如需所有基本類型的描述、陣列和元組類型的詳細資料，以及在檔案中定義新類型的步驟， Q# 請參閱[中 Q# 的類型](xref:microsoft.quantum.guide.types)。

### <a name="expressions"></a>運算式
程式設計語言中的運算式是一或多個常數、變數、運算子和函式的組合，程式語言會將其解讀並評估為特定值。
最簡單的說，針對語言中的每個型別，該型別的運算式可以是*常*值或系結至該型別之值的符號。
例如， `5` 是常值 `Int` (因此也是) 類型的運算式 `Int` ，如果符號系結 `count` 至整數值 `5` ，則 `count` 也是一個整數運算式。

此外，運算式可以由特定運算子所結合的其他運算式所組成。
例如，另一個 `Int` 評估為的運算式 `5` 是 `2+3` 。

如需中運算式和相容運算子的詳細資訊 Q# ，請參閱[中 Q# 的類型運算式](xref:microsoft.quantum.guide.expressions)。 

### <a name="statements"></a>陳述式 
語句是命令式程式設計語言的語法單位，表示要執行的一些動作。語句與語句中的運算式對比不會傳回結果，而且只會針對其副作用執行。 不過，運算式一律會傳回結果，而且通常完全不會有副作用。 簡言之， Q# 會執行語句，而運算式會進行評估。

在中，有一個簡單的語句範例 Q# ，就是將符號指派給運算式：
```qsharp
let count = 5;
```

更有趣的範例是 `for` 支援反復專案並包含*語句區塊*的語句。
假設 `qubits` 是系結至 (qubits 的暫存器（類型為技術 `Qubit[]` ）的符號，或 `Qubit`) 的類型陣列。 結果為
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
這是一種語句，它會逐一查看暫存器中的每個 qubit，對每一個的執行作業 `H` 。 請注意， `H(qubit);` 本身也是語句。

您可以使用任何類型的呼叫運算式 `Unit` (`Unit` 類型不會傳回任何資訊) 作為語句。
在傳回的 qubits 上呼叫作業時，這種類型的運算式很有用， `Unit` 因為語句的目的是要修改隱含的量子狀態。
運算式評估語句需要結尾的分號。

您可以使用語句來建立幾乎每個程式的各個層面 Q# ，而且沒有任何單一頁面可以包含與它們相關的所有資訊。
如需其詞法結構和格式的詳細資訊，請參閱檔案[ Q# 結構](xref:microsoft.quantum.guide.filestructure); 針對符號系結指派和範圍，請參閱[中 Q# 的變數](xref:microsoft.quantum.guide.variables); 如需控制流程迴圈，請參閱 `for` [中 Q# 的控制流程](xref:microsoft.quantum.guide.controlflow)。

## <a name="next-steps"></a>後續步驟

開始瞭解[中的 Q# 類型](xref:microsoft.quantum.guide.types)。

如需更多關於基礎和動機背後的背景資訊 Q# ，請參閱[為什麼我們需要 Q# ？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。
