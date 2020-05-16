---
title: '問 # 基本概念'
description: Q 的基本概念#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: fd0ea47f00b1456ec460808ef7d451c8427677cd
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431150"
---
# <a name="q-basics"></a>問 # 基本概念

在本節中，我們將簡短介紹 Q # 的基本組建區塊。

如需快速概覽問 # 是什麼，以及它如何融入作為量子開發工具組的基礎元件，您可以查看[什麼是問 #？](xref:microsoft.quantum.overview.q-sharp)。 

## <a name="what-is-a-quantum-program"></a>什麼是量副程式？

從技術觀點來看，配量程式可視為一組特定的傳統副程式，在呼叫時，會在量子系統上執行某些作業。
該觀點的重要結果是，以 Q # 撰寫的程式並不會直接 qubits 本身的模型，而是說明傳統的控制項電腦與這些 qubits 的互動方式。
根據設計，Q # 因此不會直接定義配量狀態或其他的量子機制屬性。
例如，請考慮「量子計算概念指南」中所討論的 state $ \ket{+} = \left （\ket {0} + \ket {1} \right）/\sqrt {2} $。 [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)
若要在 Q # 中準備此狀態，我們會使用 qubits 在 $ \ket $ 狀態中初始化的事實 {0} ，以及 $ \ket{+} = H\ket {0} $，其中 $H $ 是 Hadamard 轉換，其中的 [ `H` operation] （] （x：）會執行下列動作：

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a>Q 中的量子狀態#

重要的是，在撰寫上述程式時，我們並未明確參考 Q # 內的狀態，而是說明我們的程式如何*轉換*狀態。
這可讓我們完全無從得知每個目的電腦上的量子狀態為何，這*可能會有*不同的解讀，視電腦而定。 

Q # 程式無法 introspect 至 qubit 的狀態。
相反地，程式可以呼叫作業（例如） [`Measure`](xref:microsoft.quantum.intrinsic.measure) 以從 qubit 中學習資訊，以及呼叫和之類的作業 [`X`](xref:microsoft.quantum.intrinsic.x) 來處理 [`H`](xref:microsoft.quantum.intrinsic.h) qubit 的狀態。
這些作業實際*執行*的動作，只會由我們用來執行特定 Q # 程式的目的電腦進行具體處理。
例如，如果在我們的[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器上執行程式，模擬器將會對模擬的量子系統執行對應的數學運算。
但在未來，當目的機器是實際的量子電腦時，在 Q # 中呼叫這類作業會引導量子電腦在*實際*的量子系統上執行相對應的*實際*操作（例如，精確的時間間隔雷射脈衝）。

Q # 程式會依照目的電腦的定義來 recombines 這些作業，以建立更高層級的新作業來表示量子計算。
如此一來，Q # 可讓您輕鬆地表達基礎配量和混合式量子–傳統演算法的邏輯，同時也會與目的機器或模擬器的結構有關。

## <a name="q-operations-and-functions"></a>Q # 作業和函數

具體而言，Q # 程式是由*作業*、*函數*和任何使用者定義型別所組成。 

作業是用來描述量子系統的轉換，而且是 Q # 程式的最基本建立區塊。 在 Q # 中定義的每個作業，都可以呼叫任何數目的其他作業。

相對於作業，函數是用來描述純粹具*決定性*的傳統行為，而且除了計算傳統值以外，也不會有任何影響。 例如，假設我們想要測量程式結尾的 qubits，並將量測結果新增至陣列。
在此情況下，這項作業會 `Measure` 指示目的電腦對（real 或模擬） qubits 執行測量，而將傳回的結果新增至陣列的傳統程式將由函式處理。 *operation* *functions*

作業和函式統稱為*callables*，且其基礎結構和行為會引進于[Q # 頁面中的作業和](xref:microsoft.quantum.guide.operationsfunctions)函式。


## <a name="q-syntax-overview"></a>Q # 語法總覽

語言的語法描述形成語法正確程式的不同符號組合。
在 Q # 中，我們可以在三個不同的群組中，將其語法的元素分類：類型、運算式和語句。

### <a name="types"></a>類型
問 # 是強型別語言，因此謹慎使用型別可以協助編譯器在編譯時期提供有關 Q # 程式的強式保證。
除了標準和量子特定的內建基本類型（例如 `Int` 、、 `Bool` `Qubit` 和 `Result` ）之外，Q # 還提供使用者定義型別的支援。
Q # 中的 [[類型](xref:microsoft.quantum.guide.types)] 頁面上會描述所有 Q # 的各種基本類型，以及陣列和元組類型的詳細資料，以及如何在 q # 檔案中定義新的類型。

### <a name="expressions"></a>運算式
程式設計語言中的運算式是一或多個常數、變數、運算子和函式的組合，程式語言會將其解讀並評估為特定值。
最簡單的說，針對語言中的每個型別，該型別的運算式可以是*常*值或系結至該型別之值的符號。
例如， `5` 是 `Int` 常值（也是類型的運算式 `Int` ），而且如果符號系結 `count` 至整數值 `5` ，則 `count` 也是整數運算式。

此外，運算式可以包含與特定運算子結合的其他運算式。
因此，評估為的另一個 `Int` 運算式範例 `5` 是 `2+3` 。

問 # 頁面中的[類型運算式](xref:microsoft.quantum.guide.expressions)會詳細說明 q # 中類型的可能運算式，以及可以用來形成它們的相容運算子。 

### <a name="statements"></a>陳述式 
語句是命令式程式設計語言的語法單位，表示要執行的一些動作。語句與語句中的運算式對比不會傳回結果，而且只會針對其副作用執行，而運算式一律會傳回結果，而且通常不會有副作用。
這項區別經常會以用語來觀察：評估運算式，而執行語句。

問 # 中的一個非常基本的語句範例，就是將符號指派給運算式：
```qsharp
let count = 5;
```

稍微有趣的範例是 `for` 支援反復專案並包含*語句區塊*的語句。
假設是系結至 qubits 暫存器的 `qubits` 符號（技術上的類型，也就是 `Qubit[]` 類型的陣列 `Qubit` ）。 結果為
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
這是一種語句，會逐一查看暫存器中的每個 qubit，在 `H` 每個上執行作業。 請注意， `H(qubit);` 本身也是語句。

事實上，任何類型的呼叫運算式 `Unit` （不會傳回任何資訊的 callables）都可以當做語句使用。
這主要是在傳回的 qubits 上呼叫作業時使用， `Unit` 因為語句的目的是要修改隱含的量子狀態。
運算式評估語句需要結尾的分號。

幾乎所有的 Q # 程式層面都是使用語句來建立的，因此沒有任何單一頁面可以包含與它們相關的所有資訊。
不過，其詞法結構和格式會在 [ [q # 檔案結構](xref:microsoft.quantum.guide.filestructure)] 頁面、[符號系結指派] 和 [q [# 中的變數](xref:microsoft.quantum.guide.variables)範圍] 和 [控制流程] 迴圈（例如 `for` [q # 中的控制流程](xref:microsoft.quantum.guide.controlflow)）中說明。


## <a name="whats-next"></a>下一步
在本指南的其餘部分中，我們將示範如何使用 Q #，透過作業、函式和類型的基本構件來建立複雜的配量程式。

若要開始使用，您可以開始瞭解[問 # 中的類型](xref:microsoft.quantum.guide.types)。

如果您有興趣深入瞭解問 # 背後的基礎和動機，請查看[為何需要問 #？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。
