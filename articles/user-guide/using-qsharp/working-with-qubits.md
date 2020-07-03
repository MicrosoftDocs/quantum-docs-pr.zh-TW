---
title: 使用量子位元
description: 填滿描述
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 1655d18ab9d8638ad356e6fb90994b5c1fd76a25
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885306"
---
# <a name="working-with-qubits"></a>使用量子位元

Qubits 是量子運算中資訊的基本物件。 如需 qubits 的一般簡介，請參閱瞭解配量[計算](xref:microsoft.quantum.overview.understanding)，若要深入瞭解其數學表示，請參閱[Qubit](xref:microsoft.quantum.concepts.qubit)。 

本文將探討如何在 Q # 程式中使用和處理 qubits。 

> [!IMPORTANT]
>本文中所討論的語句都不是在函式主體內有效。 只有在作業內才有效。

## <a name="allocating-qubits"></a>配置 Qubits

因為實體 qubits 在量子電腦中是寶貴的資源，所以編譯器作業的一部分是要確保它們能夠盡可能有效率地使用。
因此，您需要指示 Q # 來*配置*qubits，以便在特定的語句區塊中使用。
您可以將 qubits 配置為單一 qubit，或做為 qubits 的陣列（稱為暫存器 *）。* 

### <a name="clean-qubits"></a>清除 qubits

使用 `using` 語句來配置新的 qubits，以便在語句區塊期間使用。

語句包含關鍵字 `using` ，後面接著以括弧括住的系結 `( )` ，以及 qubits 可用的語句區塊。
系結遵循與語句相同的模式 `let` ：單一符號或符號的元組，後面接著等號 `=` ，以及單一值或相符的*初始化運算式*元組。

初始化運算式適用于單一 qubit，表示為 `Qubit()` ，或 qubits 的陣列， `Qubit[n]` 其中 `n` 是 `Int` 運算式。
例如，

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

以這種方式配置的任何 qubits 從 $ \ket {0} $ 狀態開始。 因此，在上一個範例中， `auxiliary` 是 state $ \ket $ 的單一 qubit {0} ，而且 `register` 是在五個 qubit 狀態 $ \ket = \ket \otimes \ket \otimes \cdots \otimes {00000} {0} {0} \ket {0} $。
在區塊結尾時 `using` ，該區塊所配置的任何 qubits 都會立即解除配置，而且無法再使用。

> [!WARNING]
> 目的機器可以重複使用已解除配置的 qubits，並將其提供給其他 `using` 區塊進行配置。 因此，目的電腦預期 qubits 在 {0} 解除配置之前會立即處於 $ \ket $ 狀態。
> 可能的話，請使用單一作業將任何已配置的 qubits 傳回到 $ \ket {0} $。
> 如果需要，您可以使用作業，此作業會藉 @"microsoft.quantum.intrinsic.reset" 由測量來將 qubit 傳回 $ \ket {0} $，並根據結果有條件地執行作業。 這類量測會損毀具有剩餘 qubits 的任何會任何牽連，因而影響計算。


### <a name="borrowed-qubits"></a>借用的 Qubits

使用 `borrowing` 語句來配置 qubits 以供暫時使用，而不需要處於特定狀態。

在計算期間，您可以使用借用的 qubits 作為臨時空間。
這些 qubits 通常不是處於乾淨狀態，也就是說，它們不一定會在已知狀態中初始化，例如 $ \ket {0} $。
這些通常稱為「已變更」 qubits，因為它們的狀態是未知的，甚至可以與量子電腦記憶體的其他部分光子。

系結遵循與語句相同的模式和規則 `using` 。
例如，
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
借用的 qubits 處於不明狀態，超出語句區塊結尾的範圍。
借方會認可，使 qubits 在其借用時處於相同的狀態;也就是說，在語句區塊的開頭和結尾的狀態應該相同。
因為此狀態不一定是傳統狀態，所以在大部分的情況下，借用範圍都不應該包含度量。 

當借用 qubits 時，系統會先嘗試從使用中的 qubits 填入要求，但不會在語句主體期間存取 `borrowing` 。
如果沒有足夠的 qubits，則會配置新的 qubits 來完成要求。

在已變更 qubits 的已知使用案例中，是多個受控制 CNOT-CONTAINS 閘道的實作為，只需要極少的 qubits 和 incrementers。
如需如何在 Q # 中使用的範例，請參閱本文章中的[借用 Qubits 範例](#borrowing-qubits-example)，或[*使用具有以 Toffoli 為基礎之模組化乘法*](https://arxiv.org/abs/1611.07995)（Haner、Roetteler 和 Svore 2017）的 Qubits 的檔，以取得利用借用 Qubits 的演算法。

## <a name="intrinsic-operations"></a>內部作業

一旦配置之後，您就可以將 qubit 傳遞至函數和作業。
在某種意義上，這就是問 # 程式可以使用 qubit 執行的動作，因為可以採取的動作全都定義為作業。

本文討論幾個實用的 Q # 作業，可讓您用來與 qubits 互動。
如需這些和其他專案的詳細資訊，請參閱[內部作業和函數](xref:microsoft.quantum.libraries.standard.prelude)。 

首先，單一 qubit 的 Pauli 運算子 $X $、$Y $ 和 $Z $ 會由內部作業（和）以 Q # 表示，而 [`X`](xref:microsoft.quantum.intrinsic.x) [`Y`](xref:microsoft.quantum.intrinsic.y) [`Z`](xref:microsoft.quantum.intrinsic.z) 每一個都有類型 `(Qubit => Unit is Adj + Ctl)` 。

如[內部作業和](xref:microsoft.quantum.libraries.standard.prelude)函式中所述，請將 $X $，而 `X` 不是閘道。
您可以使用作業 `X` 來準備 s_1 \dots .. s_n} $ 格式的 s_0 的狀態，以取得某些傳統位字串 $s $：

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> 稍後，您將會看到更精簡的方式來撰寫此作業，而不需要手動控制流程。

您也可以使用 \Right 轉換 $H $ 來準備狀態，例如 $ \ket{+} = \left （\ket {0} + \ket {1} \sqrt）/\ket {2} $ 和 $ \left {-} = \ket （\ket {0} -\right {1} \sqrt）/Hadamard {2} $，方法是透過內建作業 [`H`](xref:microsoft.quantum.intrinsic.h) （也屬於類型（Qubit => 單位為形容詞 + Ctl））在 Q # 中表示）：

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>量測

個別 qubits 的測量可以用不同的基底執行，每個都是由[Bloch 球體](xref:microsoft.quantum.glossary#bloch-sphere)上的 Pauli 軸表示。
*計算基礎*是指 `PauliZ` 基礎，而且是用於測量的最常見基礎。

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a>以基礎測量單一 qubit `PauliZ`

使用作業 [`M`](xref:microsoft.quantum.intrinsic.m) ，這是內建的內建函式非單一作業，可依基礎測量單一 qubit， `PauliZ` 並將傳統值指派給結果。
`M`具有保留的傳回類型， `Result` 它只能接受值 `Zero` 或 `One` 對應至測量的狀態 $ \ket {0} $ 或 $ \ket {1} $-表示結果不再是配量狀態。

下列作業是一個簡單的範例，它會在 $ \ket $ 狀態中配置一個 qubit {0} ，然後對它套用 Hadamard 作業 `H` 並測量結果 `PauliZ` 。

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a>測量特定基底中的一或多個 qubits

若要測量特定基底中一個或多個 qubits 的陣列，您可以使用作業 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 。

的輸入 `Measure` 是類型的陣列 `Pauli` （例如）， `[PauliX, PauliZ, PauliZ]` 以及 qubits 的陣列。

下列作業會提供稍微較複雜的範例，如果類型的暫存器中的 `true` 所有 qubits 在以 `Qubit[]` 指定的 Pauli 為基礎進行測量時，則會傳回布林值，否則會傳回 `false` 。

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

請注意，此範例 `Measure` 一次只會在個別的 qubits 上執行，但作業可以延伸到多個 qubits 的聯合測量。

## <a name="borrowing-qubits-example"></a>借用 Qubits 範例

Canon 中有一些使用關鍵字的範例 `borrowing` ，例如下列函數 `MultiControlledXBorrow` 。 如果 `controls` 代表要加入至作業的控制項 qubits `X` ，則此實作為新增的已變更[ancillas](xref:microsoft.quantum.glossary#ancilla)數目為 `Length(controls)-2` 。

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

請注意，此範例使用結合的廣泛用法 `With` ，其格式適用于支援 adjoint 的作業，例如 `WithA` 。
這是很好的程式設計風格，因為將控制項加入至包含的結構只會將 `With` 控制項傳播至內部作業。
另請注意，除了作業的 `body` 之外，也會 `controlled` 明確提供作業主體的執行，而不是使用 `controlled auto` 語句。
原因是，因為線路的結構，所以您可以輕鬆地加入進一步的控制項，相較于將控制項加入至中的每個閘道，這是很有説明的 `body` 。 

比較這段程式碼與另一個 canon 函式是有意義的，它會 `MultiControlledXClean` 達到相同的目標來執行乘以控制的作業 `X` ，不過，它使用了使用機制的幾個乾淨 qubits `using` 。 

## <a name="next-steps"></a>接下來的步驟

瞭解 Q # 中的[控制流程](xref:microsoft.quantum.guide.controlflow)。