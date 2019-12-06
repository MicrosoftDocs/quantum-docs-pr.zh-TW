---
title: '問 # 標準程式庫-錯誤更正 |Microsoft Docs'
description: '問 # 標準程式庫-錯誤更正'
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e1b78cf94ae0a043ad275d4cb06b230eafd7fc85
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863192"
---
# <a name="error-correction"></a>錯誤修正 #

## <a name="introduction"></a>簡介 ##

在傳統運算中，如果您想要保護一點以避免發生錯誤，通常可以重復資料位來表示該位的*邏輯位*。
比方說，let $ \overline{0} = $0 是資料位0的編碼方式，我們使用標籤0上方的一條線來表示它是0狀態中位的編碼方式。
如果同樣地，讓 $ \overline{1} = $111，則會有一個簡單的重複程式碼，可防止任何一位翻轉錯誤。
也就是說，如果有三個位的任何一個翻轉，我們就可以採取多數投票來復原邏輯位的狀態。
雖然傳統錯誤修正是此特定範例（建議不[起毛的編碼理論簡介](https://www.springer.com/us/book/9783540641339)）的更豐富主旨，但上述重複程式碼已指向保護配量資訊的可能問題。
換句話說，「[無複製定理](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem)」表示如果我們測量每個個別的 qubit，並使用上述的傳統程式碼來進行大部分的投票，我們就會遺失我們嘗試保護的精確資訊。

在 [配量] 設定中，我們會看到度量有問題。 我們仍然可以執行上述編碼。
這麼做有助於瞭解如何將錯誤更正一般化至量子案例。
因此，let $ \ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$，並讓 $ \ket{\overline{1}} = \ket{111}$。
然後，藉由線性，我們為所有輸入定義了重複的程式碼;例如，$ \ket{\overline{+}} = （\ket{\overline{0}} + \ket{\overline{1}}）/\sqrt{2} = （\ket{000} + \ket{111}）/\sqrt{2}$。
特別是，在中間 qubit 上 $X _1 $ act 時，我們會看到兩個分支中所需的更正精確 $X _1 $： $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left （X_1 \ket{000} + X_1 \ket{111} \right） \\\\ & = \frac{1}{\sqrt{2}} \left （\ket{010} + \ket{101} \right）。
\end{align} $ $

若要瞭解如何找出這種情況，而不測量我們嘗試保護的非常狀態，請記下每個不同的位會翻轉錯誤對我們的邏輯狀態的意義：

| 錯誤 $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ |
| --- | --- | --- |
| $ \boldone $ | $ \ket{000}$ | $ \ket{111}$ |
| $X_0$ | $ \ket{100}$ | $ \ket{011}$ |
| $X_1$ | $ \ket{010}$ | $ \ket{101}$ |
| $X_2$ | $ \ket{001}$ | $ \ket{110}$ |

為了保護我們所編碼的狀態，我們必須能夠區分彼此和身分識別 $ \boldone $ 之間的三個錯誤，而不區分 $ \ket{\overline{0}} $ 和 $ \ket{\overline{1}} $。
例如，如果我們測量 $Z _0 $，在無錯誤情況下，我們會針對 $ \ket{\overline{0}} $ 和 $ \ket{\overline{1}} $ 取得不同的結果，因此會折迭編碼的狀態。
另一方面，請考慮測量 $Z _0 Z_1 $，這是每個計算基礎狀態中前兩個位的同位檢查。
回想一下，Pauli 運算子的每個測量都會檢查要測量的狀態會對應到哪個 eigenvalue，因此針對上表中的每個 state $ \ket{\psi} $，我們可以計算 $Z _0 Z_1 \ket{\psi} $ 來查看是否取得 $ \pm\ket{\psi} $。
請注意，$Z _0 Z_1 \ket{000} = \ket{000}$，該 $Z _0 Z_1 \ket{111} = \ket{111}$，如此一來，我們就會得出這項測量的結果，使兩者的編碼狀態相同。
另一方面，$Z _0 Z_1 \ket{100} =-\ket{100}$ and $Z _0 Z_1 \ket{011} =-\ket{011}$，因此測量 $Z _0 Z_1 $ 的結果，會顯示有關發生錯誤的實用資訊。

為了強調此情況，我們會重複上表，但在每個資料列上新增測量 $Z _0 Z_1 $ 和 $Z _1 Z_2 $ 的結果。
我們會以觀察到的 eigenvalue 正負號（$ + $ 或 $-$）來表示每個測量的結果，分別對應至 `Zero` 和 `One`的 Q # `Result` 值。

| 錯誤 $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ | $Z _0 Z_1 $ 的結果 | $Z _1 Z_2 $ 的結果 |
| --- | --- | --- | --- | --- |
| $ \boldone $ | $ \ket{000}$ | $ \ket{111}$ | $+$ | $+$ |
| $X_0$ | $ \ket{100}$ | $ \ket{011}$ | $-$ | $+$ |
| $X_1$ | $ \ket{010}$ | $ \ket{101}$ | $-$ | $-$ |
| $X_2$ | $ \ket{001}$ | $ \ket{110}$ | $+$ | $-$ |

因此，這兩個度量的結果會唯一判斷發生的位翻轉錯誤，但不會顯示我們所編碼之狀態的任何相關資訊。
我們將這些結果稱為「*症狀*」，並參考將症狀對應到導致它復原的錯誤的*程式。*
特別是，我們強調復原是一種*傳統*的推斷程式，它會將發生的症狀視為其輸入，並傳回如何修正可能發生之任何錯誤的處方。

> [!NOTE]
> 上述的位翻轉程式碼只能針對單一的位翻轉錯誤進行更正;也就是在單一 qubit 上運作的 `X` 作業。
> 將 `X` 套用至一個以上的 qubit 會在復原後，將 $ \ket{\overline{0}} $ 對應到 $ \ket{\overline{1}} $。
> 同樣地，套用階段翻轉作業 `Z` 會將 $ \ket{\overline{1}} $ 對應至 $-\ket{\overline{1}} $，因此會將 $ \ket{\overline{+}} $ 對應至 $ \ket{\overline{-}} $。
> 一般來說，可以建立代碼來處理較大的錯誤數目，以及處理 $Z $ 錯誤以及 $X $ 錯誤。

我們可以在對所有程式碼狀態採取相同方式的量子錯誤更正中描述度量的深入解析，就是穩定的*形式*的本質。
Q # canon 提供了一個架構，可描述從穩定程式碼進行編碼和解碼，以及描述如何從錯誤中復原。
在本節中，我們會將此架構及其應用程式描述為一些簡單的量子錯誤更正代碼。

> [!TIP]
> 完整的穩定形式簡介已超出本節的範圍。
> 我們參考讀者有興趣深入瞭解[Gottesman 2009](https://arxiv.org/abs/0904.2557)。

## <a name="representing-error-correcting-codes-in-q"></a>代表 Q 中的錯誤修正代碼# ##

為了協助指定錯誤更正代碼，Q # canon 會提供數個不同的使用者定義類型：

- <xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`：表示 qubits 的暫存器應解讀為錯誤更正程式碼的程式碼區塊。
- <xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`：表示測量結果的陣列應解讀為在程式碼區塊上測量的症狀。
- <xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`：表示應該使用*傳統*函數來解讀症狀，並傳回應套用的更正。
- <xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`：表示作業會使用 qubits 來代表資料和全新的 ancilla qubits，以便產生錯誤更正程式碼的程式碼區塊。
- <xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`：表示作業會 decompose 的程式碼區塊將錯誤修正為數據 qubits，以及用來代表症狀資訊的 ancilla qubits。
- <xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`：代表應該用來從程式碼區塊中解壓縮症狀資訊的作業，而不會影響程式碼所保護的狀態。

最後，canon 會提供 <xref:microsoft.quantum.errorcorrection.qecc> 類型，以收集定義配量錯誤更正程式碼所需的其他類型。 與每個穩定配量代碼相關聯的程式碼長度 $n $、邏輯 qubits 的 $k $，以及 $d $ 的最小距離，通常會以標記法⟦ $n $，$k $，$d $ ⟧中，以方便群組在一起。 例如，<xref:microsoft.quantum.errorcorrection.bitflipcode> 函式會定義⟦3，1，1⟧位翻轉程式碼：

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

請注意，`QECC` 類型不*包含復原*功能。
這可讓我們變更用於更正錯誤的復原功能，而不需變更程式碼本身的定義;這項功能特別適用于將特性度量的意見反應納入復原所假設的模型中。

以這種方式定義程式碼之後，我們可以使用 <xref:microsoft.quantum.errorcorrection.recover> 作業從錯誤中復原：

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

我們會在[位翻轉程式碼範例](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)中更詳細地探索此功能。

除了比對程式碼之外，還提供了[五個 qubit 完美程式](https://arxiv.org/abs/quant-ph/9602019)代碼的 canon，以及[七 qubit 的程式碼](https://arxiv.org/abs/quant-ph/9705052)，兩者都可以更正任意的單一 qubit 錯誤。
