---
title: Q# 基礎
description: 的基本概念 Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 86f6538cf383f4e7c14255b38cfb1c141c8f991b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835514"
---
# <a name="no-locq-basics"></a>Q# 基礎

本文提供的基本組建區塊簡介 Q# 。

如需瞭解什麼是什麼， Q# 以及它如何納入作為量子開發工具組的基礎元件，請參閱 [何謂 Q# ？](xref:microsoft.quantum.overview.q-sharp)。 

## <a name="what-is-a-quantum-program"></a>什麼是量副程式？

從技術觀點來看，量副程式是一組特定的傳統副程式，在呼叫時，會在量子系統上執行某些作業。
該觀點的重要結果是，程式不 Q# 會直接建立量子位本身的模型，而是說明傳統方式控制的電腦如何與這些量子位互動。
根據設計，不 Q# 會直接定義量子狀態或量子機制的其他屬性。
比方說，請考慮「量子運算概念指南」中所討論的「狀態 $ \ket{+} = \left ( \ket {0} + \ket {1} \right) /\sqrt {2} $。 [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)
若要在中準備此狀態 Q# ，請從量子位在 $ \ket $ 狀態中初始化的事實開始， {0} 以及該 $ \ket{+} = H\ket {0} $，其中 $H $ 是[ `H` 作業所](xref:microsoft.quantum.intrinsic.h)執行的[Hadamard 轉換](xref:microsoft.quantum.glossary#hadamard)。 初始化和轉換量子位的基本程式碼，如下所 Q# 示：

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
如需 *初始化或配置*量子位的詳細資訊，請參閱 [使用量子位](xref:microsoft.quantum.guide.qubits)。

## <a name="quantum-states-in-no-locq"></a>中的量子狀態 Q#

重要的是，先前的程式並不會明確參考內的狀態， Q# 但會說明我們的程式如何 *轉換* 狀態。
使用這種方法時，您可以完全無從確定每個目的電腦 *上的* 量子狀態為何，根據電腦而定，可能會有不同的解釋。 

Q#程式無法 introspect 至量子位的狀態。
相反地，程式可以呼叫的作業（例如， [`Measure`](xref:microsoft.quantum.intrinsic.measure) 從量子位中學習資訊），然後呼叫和之類的作業 [`X`](xref:microsoft.quantum.intrinsic.x) 來處理 [`H`](xref:microsoft.quantum.intrinsic.h) 量子位的狀態。
這些作業實際 *執行* 的動作，只會由用來執行特定程式的目的電腦來具體處理 Q# 。
例如，如果在我們的 [完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器上執行程式，模擬器會對模擬的量子系統執行對應的數學運算。
但在未來，當目的電腦是真實量子電腦時，在中呼叫這類操作會 Q# 引導量子電腦在*真正*的量子系統上執行對應的*實際*操作，例如，精確地計時的雷射脈衝) 。

Q#程式會 recombines 目的電腦所定義的這些作業，以建立新的較高層級作業來表示量子計算。
如此一來，就能 Q# 輕鬆地表達基礎量子和混合式量子的邏輯，也就是目的電腦或模擬器的結構一般。

## <a name="no-locq-operations-and-functions"></a>Q# 作業和函式

具體而言， Q# 套裝程式含 *作業*、 *函數*和任何使用者定義型別。 

作業是用來描述量子系統的轉換，而且是最基本的程式組建區塊 Q# 。 中定義的每個 Q# 作業都會呼叫任何數目的其他作業。

與作業不同的是，函式是用來描述純粹具 *決定性* 的傳統行為，而且除了計算傳統值之外，沒有任何影響。 例如，假設您想要測量程式結尾的量子位，並將測量結果新增至陣列。
在此情況下， `Measure` 是*operation*一項作業，會指示目的電腦對 (real 或模擬) 量子位進行測量。 同樣地，函式會處理將傳回的結果新增至陣列的 *傳統處理常式* 。

作業和函數統稱為 *callables*。 中導入了其基礎結構和行為，並詳細說明[中 Q# 的作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。


## <a name="no-locq-syntax-overview"></a>Q# 語法總覽

語言的語法描述形成語法正確程式的不同符號組合。
在中 Q# ，語法元素會分類為三個不同的群組：類型、運算式和語句。

### <a name="types"></a>類型
Q# 是一種強型別語言，可讓編譯器在編譯時期提供程式的強大保證，以利使用類型 Q# 。
除了標準和量子特有的內建基本型別，例如、、 `Int` `Bool` `Qubit` 和 `Result` ，也 Q# 提供使用者定義類型的支援。

如需所有基本型別、陣列和元組類型的詳細資訊，以及在檔案中定義新類型的步驟，請 Q# 參閱[中 Q# 的類型](xref:microsoft.quantum.guide.types)。

### <a name="expressions"></a>運算式
程式設計語言中的運算式結合了一或多個常數、變數、運算子和函式，程式語言會將這些常數、變數、運算子和函式轉譯為特定值。
最簡單的方法是，針對語言中的每個類型，該類型的運算式可以是系結至該類型值的 *常* 值或符號。
例如， `5` 是 `Int` 常值 (因此也是) 類型的運算式 `Int` ，如果符號系結 `count` 至整數值 `5` ，則 `count` 也是整數運算式。

此外，運算式也可以由某些運算子所合併的其他運算式所組成。
例如，另一個 `Int` 評估為的運算式 `5` `2+3` 。

如需中運算式和相容運算子的詳細資訊 Q# ，請參閱[中 Q# 的型別運算式](xref:microsoft.quantum.guide.expressions)。 

### <a name="statements"></a>陳述式 
語句是命令式程式設計語言的語法單位，表示要執行的一些動作。語句與該語句中的運算式對比不會傳回結果，而且只會針對其副作用執行。 但是，運算式一律會傳回結果，而且通常沒有任何副作用。 簡單來說， Q# 語句是在評估運算式時執行。

在中，語句的簡單範例 Q# 是將符號指派給運算式：
```qsharp
let count = 5;
```

比較有趣的範例是 `for` 支援反覆運算的語句，並包含 *語句區塊*。
假設是系結至量子位之暫存器的 `qubits` 符號， (的型別或型別的 `Qubit[]` 陣列 `Qubit`) 。 結果為
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
這是逐一查看暫存器中的每個量子位，在每個上執行作業的語句 `H` 。 請注意，它 `H(qubit);` 本身也是語句。

您可以使用類型的任何呼叫運算式 `Unit` (`Unit` 類型不會傳回任何) 為語句的資訊。
這種類型的運算式在呼叫量子位上的作業時很有用， `Unit` 因為語句的目的是要修改隱含的量子狀態。
運算式評估語句需要終止分號。

您可以使用語句來建立幾乎每個程式的各個層面 Q# ，而且沒有任何單一頁面可以包含與它們相關的所有資訊。
如需其詞法結構和格式的詳細資訊，請參閱檔案[ Q# 結構](xref:microsoft.quantum.guide.filestructure); 針對符號系結指派和範圍，請參閱[中 Q# 的變數](xref:microsoft.quantum.guide.variables)，以及如的控制流程迴圈（例如 `for` ），請參閱[中 Q# 的控制流程](xref:microsoft.quantum.guide.controlflow)。

## <a name="next-steps"></a>後續步驟

開始瞭解[中的 Q# 類型](xref:microsoft.quantum.guide.types)。

如需背後基礎和動機的詳細背景 Q# ，請參閱 [為什麼我們需要 Q# ？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。
