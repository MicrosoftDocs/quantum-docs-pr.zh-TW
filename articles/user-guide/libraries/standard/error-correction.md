---
title: 標準程式庫中的錯誤修正 Q#
description: 瞭解如何在您的程式中使用錯誤修正程式碼， Q# 同時保護量子位的狀態。
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: dad0db4d2aab27e5ae46d4df10ee050f785d8bb8
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835548"
---
# <a name="error-correction"></a>錯誤修正 #

## <a name="introduction"></a>簡介 ##

在傳統運算中，如果您想要針對錯誤保護一點，通常可以藉由重復資料位來以 *邏輯位* 表示該位。
例如，假設 $ \overline {0} = $0 是資料位0的編碼方式，我們在標籤0上方使用一行來表示它是0狀態的位編碼。
如果我們以同樣的方式讓 $ \overline {1} = $111，則會有一個簡單的重複程式碼，可防止任何一個位翻轉錯誤。
也就是說，如果有任何三個位的翻轉，我們可以藉由進行多數投票來復原邏輯位的狀態。
雖然傳統錯誤更正是更豐富的主題，但此特定範例 (我們建議您不要加上 [編碼理論](https://www.springer.com/us/book/9783540641339)) 的簡介，但上述重複程式碼已經指向保護量子資訊的可能問題。
亦即， [不復制定理](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) 表示如果我們測量每個個別的量子位，並使用上述傳統程式碼來進行大部分的投票，則會遺失我們嘗試保護的精確資訊。

在量子設定中，我們會看到量測有問題。 我們仍然可以執行上述編碼。
若要瞭解如何將錯誤修正一般化至量子案例，這會很有説明。
因此，let $ \ket{\overline {0} } = \ket {000} = \ket {0} \otimes \ket {0} \otimes \ket {0} $，而 let $ \ket{\overline {1} } = \ket {111} $。
然後，藉由線性，我們為所有輸入定義了重複的程式碼;例如，$ \ket{\overline{+}} = ( \ket{\overline {0} } + \ket{\overline {1} } ) /\sqrt {2} = ( \ket {000} + \ket {111}) /\sqrt {2} $。
尤其是，在中間量子位上進行位翻轉誤差 $X _1 $ act，我們看到兩個分支中所需的更正精確 $X _1 $： $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac {1} {\sqrt {2} } \left ( X_1 \ket {000} + X_1 \ket {111} \right) \\ \\ & = \frac {1} {\sqrt {2} } \left ( \ket {010} + \ket {101} \right) 。
\end{align} $ $

若要瞭解我們如何找出這種情況，而不需要測量我們嘗試保護的狀態，請將每個不同的位翻轉錯誤對我們的邏輯狀態寫下：

| 錯誤 $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ |
| --- | --- | --- |
| $ \boldone $ | $ \ket {000} $ | $ \ket {111} $ |
| $X_0$ | $ \ket {100} $ | $ \ket {011} $ |
| $X_1$ | $ \ket {010} $ | $ \ket {101} $ |
| $X_2$ | $ \ket {001} $ | $ \ket {110} $ |

為了保護我們正在編碼的狀態，我們必須能夠區分三個錯誤，以及從身分識別 $ \boldone $，而不區分 $ \ket{\overline {0} } $ 和 $ \ket{\overline {1} } $。
例如，如果我們測量 $Z _0 $，我們 {0} 會在無錯誤情況下取得 $ \ket{\overline} $ 和 $ \ket{\overline} $ 的不同結果 {1} ，以折迭編碼的狀態。
相反地，請考慮測量 $Z _0 Z_1 $，這是每個計算基礎狀態中前兩個位的同位檢查。
回想一下，Pauli 運算子的每個測量都會檢查要測量的狀態對應的 eigenvalue，因此針對上表中的每個狀態 $ \ket{\psi} $，我們可以計算 $Z _0 Z_1 \ket{\psi} $，以查看我們是否取得 $ \pm\ket{\psi} $。
請注意，$Z _0 Z_1 \ket {000} = \ket {000} $，而且 $Z _0 Z_1 \ket {111} = \ket {111} $，所以我們得出這種測量結果對兩個編碼的狀態都是一樣的。
另一方面，$Z _0 Z_1 \ket {100} =-\ket {100} $ 和 $Z _0 Z_1 \ket {011} =-\ket {011} $，因此測量 $Z _0 Z_1 $ 的結果會顯示發生錯誤的實用資訊。

為了強調這一點，我們重複上述的表格，但在每個資料列上新增測量 $Z _0 Z_1 $ 和 $Z _1 Z_2 $ 的結果。
我們會以觀察到的 eigenvalue 正負號（分別是 $ + $ 或 $-$）來表示每個度量的結果，分別對應至 Q# `Result` 和的值 `Zero` `One` 。

| 錯誤 $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ | $Z _0 Z_1 $ 的結果 | $Z _1 Z_2 $ 的結果 |
| --- | --- | --- | --- | --- |
| $ \boldone $ | $ \ket {000} $ | $ \ket {111} $ | $+$ | $+$ |
| $X_0$ | $ \ket {100} $ | $ \ket {011} $ | $-$ | $+$ |
| $X_1$ | $ \ket {010} $ | $ \ket {101} $ | $-$ | $-$ |
| $X_2$ | $ \ket {001} $ | $ \ket {110} $ | $+$ | $-$ |

因此，這兩個度量的結果可唯一判斷發生的位翻轉錯誤，但不會洩漏有關我們所編碼之狀態的任何資訊。
我們將這些結果稱為*有問題*的結果，並將其重新對應至造成復原的錯誤的處理*程式。*
尤其是，我們強調的是，復原是一種 *傳統* 的推斷程式，它會將發生的症狀作為其輸入，並傳回如何修正可能發生之任何錯誤的處方。

> [!NOTE]
> 上述的位翻轉程式碼只能針對單一位翻轉錯誤進行修正;也就是 `X` 在單一量子位上運作的作業。
> 套用 `X` 至一個以上的量子位會在復原後將 $ \ket{\overline {0} } $ 對應到 $ \ket{\overline {1} } $。
> 同樣地，套用階段翻轉作業 `Z` 會將 $ \ket{\overline {1} } $ 對應到 $-\ket{\overline {1} } $，因此會將 $ \ket{\overline{+}} $ 對應到 $ \ket{\overline {-} } $。
> 更常見的情況是，您可以建立程式碼來處理更大量的錯誤，以及處理 $Z $ 錯誤以及 $X $ 錯誤。

我們可以針對在所有程式碼狀態上採取相同方式的量子錯誤修正來描述度量的深入解析，是 *穩定形式*的本質。
Q#Canon 會提供架構來描述從穩定程式碼到的編碼和解碼，以及描述如何從錯誤中復原。
在本節中，我們會將此架構和其應用程式描述為一些簡單的量子錯誤修正程式碼。

> [!TIP]
> 完整的「穩定」形式簡介已超出本節的範圍。
> 我們將讀者想要深入瞭解 [Gottesman 2009](https://arxiv.org/abs/0904.2557)。

## <a name="representing-error-correcting-codes-in-no-locq"></a>代表中的錯誤修正碼 Q# ##

為了協助指定錯誤修正碼， Q# canon 提供數種不同的使用者定義類型：

- <xref:microsoft.quantum.errorcorrection.logicalregister>`= Qubit[]`：表示應將量子位的暫存器解釋為錯誤修正程式碼的程式碼區塊。
- <xref:microsoft.quantum.errorcorrection.syndrome>`= Result[]`：表示測量結果的陣列應解釋為在程式碼區塊上測量的症狀。
- <xref:microsoft.quantum.errorcorrection.recoveryfn>`= (Syndrome -> Pauli[])`：表示應該使用*傳統*函式來解讀症狀，並傳回應該套用的更正。
- <xref:microsoft.quantum.errorcorrection.encodeop>`= ((Qubit[], Qubit[]) => LogicalRegister)`：表示某項作業會採用量子位來代表資料和全新的 ancilla 量子位，以產生錯誤修正程式碼的程式碼區塊。
- <xref:microsoft.quantum.errorcorrection.decodeop>`= (LogicalRegister => (Qubit[], Qubit[]))`：表示分解錯誤修正程式碼至資料量子位的程式碼區塊，以及用來代表症狀資訊的 ancilla 量子位的作業。
- <xref:microsoft.quantum.errorcorrection.syndromemeasop>`= (LogicalRegister => Syndrome)`：表示應該用來從程式碼區塊中解壓縮症狀資訊的作業，而不會干擾程式碼所保護的狀態。

最後，canon 會提供型別， <xref:microsoft.quantum.errorcorrection.qecc> 以收集定義量子錯誤修正程式碼時所需的其他類型。 與每個穩定程式量副程式代碼相關聯的程式碼長度 $n $、邏輯量子位的數位 $k $，以及 $d $ 的最小距離，通常會以⟦ $n $、$k $、$d $ ⟧的標記法來群組在一起。 例如，函數會 <xref:microsoft.quantum.errorcorrection.bitflipcode> 定義⟦3，1，1⟧位翻轉程式碼：

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

請注意，此 `QECC` 類型 *不* 包含復原功能。
這可讓我們變更修復錯誤所用的復原函式，而不需要變更程式碼本身的定義;這項功能特別適用于將特徵測量的意見反應納入復原所假設的模型中。

以這種方式定義程式碼之後，我們就可以使用此作業 <xref:microsoft.quantum.errorcorrection.recover> 從錯誤中復原：

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

我們將在 [位翻轉程式碼範例](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code)中更詳細地探索這一點。

除了位翻轉程式碼之外， Q# canon 還提供了 [五量子位的完美程式碼](https://arxiv.org/abs/quant-ph/9602019)和 [七量子位的程式碼](https://arxiv.org/abs/quant-ph/9705052)，這兩者都可以更正任意的單一量子位錯誤。
