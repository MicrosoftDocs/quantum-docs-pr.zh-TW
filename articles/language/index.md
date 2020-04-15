---
title: Q# 程式設計語言
description: 適用於量子程式開發的 Q# 語言簡介。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: b62e6866fc3609d95c26a5eab2a6eac325dfe330
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907370"
---
# <a name="the-q-programming-language"></a>Q# 程式設計語言

## <a name="introduction"></a>簡介

量子運算的自然模型是將量子電腦視為副處理器，類似於 GPU、FPGA 和其他附屬處理器所使用的模型。
主要控制邏輯會在傳統「主機」電腦上執行傳統程式碼。
若適當且必要，主機程式便可叫用會在附屬處理器上執行的副程式。
當副程式完成時，主機程式便會存取副程式的結果。

Q# (Q-sharp) 是用來表示量子演算法的領域專屬程式設計語言。
其可在傳統主機程式和電腦的控制下，用來編寫會在附屬量子處理器上執行的副程式。
在量子處理器可供廣泛使用之前，Q# 副程式會在模擬器上執行。

Q# 提供了一組小型的基本類型，以及兩種方式 (陣列和元組) 來建立新的結構化類型。
其支援基本程序模型，可供使用迴圈和 if/then 陳述式來編寫程式。
Q# 中的最上層建構是使用者定義的類型、操作和函式。

下列各節會詳細說明：
- [類型模型](xref:microsoft.quantum.language.type-model)
- [運算式](xref:microsoft.quantum.language.expressions)
- [陳述式](xref:microsoft.quantum.language.statements)
- [檔案結構](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a>慣例

我們努力在確保所有情況下都會一致地使用常見標點符號。
我們希望這麼做能夠讓您更容易學習和閱讀 Q#，因為這些標點符號永遠會代表相同的東西，而且相同的概念永遠會以相同的方式來表示。

具體來說：

- 分號 (`;`)，用來結束陳述式或單行指示詞。
  分號不會用於其他用途。
- 逗號 (`,`)，用來分隔序列的元素。 逗號會用於元組常值、陣列常值、引數清單、元組定義和類型清單。 **和舊版不同的是，不再支援以 `;` 作為陣列常值分隔符號。**
- 冒號 (`:`)，用來引入類型註釋。 冒號主要用在可呼叫的簽章中。
  因為冒號一律會引進類型簽章，所以在 0.3 中引進的三元條件運算子會使用分隔號 (`|`) 來分隔 true 和 false 值；因此，Q# 會使用 `cond ? tval | fval` (而不是冒號) 來作為 C 中的分隔符號。
  
