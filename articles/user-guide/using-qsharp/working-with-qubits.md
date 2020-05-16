---
title: 使用量子位元
description: 填滿描述
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: e89b9ccfe2a0796e01eedfc99f7ce71038d85f38
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430929"
---
# <a name="working-with-qubits"></a>使用量子位元

現在看過各種不同的 Q # 語言部分，讓我們深入瞭解，並瞭解如何使用 qubits 本身。

請注意，函式的主體中不允許任何這些語句。
只有在作業內才有效。

## <a name="allocating-qubits"></a>配置 Qubits

### <a name="clean-qubits"></a>清除 qubits

`using`語句是用來*配置*新的 qubits，以便在語句區塊期間使用。

語句包含關鍵字 `using` ，後面接著左括弧、系結 `(` 、右括弧 `)` 和語句區塊，可在其中使用 qubits。
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

以這種方式配置的任何 qubits 從 $ \ket {0} $ 狀態開始，在上述範例中， `register` 會在 state $ \ket {00000} = \ket \otimes \ket \otimes \cdots \otimes {0} {0} \ket $ 中啟動 {0} 。
在區塊結尾時 `using` ，該區塊所配置的任何 qubits 都會立即解除配置，而且無法再使用。

> [!WARNING]
> 目的機器預期 qubits 在 {0} 解除配置之前會立即處於 $ \ket $ 狀態，以便可以重複使用並提供給其他 `using` 區塊進行配置。
> 可能的話，請使用單一作業將任何已配置的 qubits 傳回到 $ \ket {0} $。
> 如果需要，您 @"microsoft.quantum.intrinsic.reset" 可以使用作業來測量 qubit，並使用該測量結果來確保測量的 qubit 會傳回 $ \ket {0} $。 這類測量會摧毀具有剩餘 qubits 的任何會任何牽連，因此會影響計算。


### <a name="borrowed-qubits"></a>借用的 Qubits

`borrowing`語句是用來讓 qubits 可供暫時使用，而不需要處於特定狀態。

「借款」機制可讓您配置 qubits，在計算期間用來做為臨時空間。
這些 qubits 通常不是處於乾淨狀態，也就是說，它們不一定會在已知狀態中初始化，例如 $ \ket {0} $。
這些通常稱為「已變更」 qubits，因為它們的狀態是未知的，甚至可以與量子電腦記憶體的其他部分光子。

系結會遵循與語句中的相同模式和規則 `using` 。
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
借方會認可，使 qubits 處於借用時的相同狀態，也就是其在語句區塊開頭和結尾的狀態應該是相同的。
此狀態特別不一定是傳統狀態，因此在大部分情況下，借用範圍不應包含測量。 

當借用 qubits 時，系統會先嘗試從使用中的 qubits 填入要求，但不會在語句主體期間存取 `borrowing` 。
如果沒有足夠的 qubits，則會配置新的 qubits 來完成要求。


在已變更 qubits 的已知使用案例中，是多個受控制 CNOT-CONTAINS 閘道的實作為，只需要極少的 qubits 和 incrementers。
請參閱下列[借用 Qubits 範例](#borrowing-qubits-example)，以查看在 Q # 中使用的範例，或[*使用具有以 Toffoli 為基礎之模組化乘法*](https://arxiv.org/abs/1611.07995)（Haner、Roetteler 和 Svore 2017）的 Qubits，針對利用借用 Qubits 的演算法來進行檔的分解。


## <a name="intrinsic-operations"></a>內部作業

一旦配置之後，就可以將 qubit 傳遞至函數和作業。
在某種意義上，這就是問 # 程式可以使用 qubit 執行的動作，因為可以採取的動作全都定義為作業。
我們會在內建[作業和](xref:microsoft.quantum.libraries.standard.prelude)函式中更詳細地看到這些作業，但目前我們提到一些可用來與 qubits 互動的實用作業。

首先，單一 qubit 的 Pauli 運算子 $X $、$Y $ 和 $Z $ 會由內部作業（和）以 Q # 表示，而 `X` `Y` `Z` 每一個都有類型 `(Qubit => Unit is Adj + Ctl)` 。
如[內部作業和](xref:microsoft.quantum.libraries.standard.prelude)函式中所述，我們可以將 $X $ 和， `X` 視為不使用閘道的運算。
此作業 `X` 可讓我們針對某些傳統位字串 $s $，準備表單 $ \ket{s_0 s_1 \dots .. s_n} $ 的狀態：

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
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> 之後，我們會看到更精簡的方式來撰寫此作業，而不需要手動進行流量控制。

我們也可以使用 \Right 轉換 $H $ 來準備狀態，例如 $ \ket{+} = \left （\ket {0} + \ket {1} \sqrt）/\ket {2} $ and $ \left {-} = \ket （\ket {0} -\right {1} \sqrt）/Hadamard {2} $，方法是透過內部作業，在 Q # 中表示 `H : (Qubit => Unit is Adj + Ctl)` ：

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>量測

使用作業 `Measure` ，這是內建的內建函式非單一作業，我們可以從類型的物件中提取傳統資訊， `Qubit` 並指派傳統值做為結果（具有保留類型 `Result` ），表示結果不再是配量狀態。
的輸入 `Measure` 是 Bloch 球體上的 Pauli 軸，以類型的值 `Pauli` （例如 `PauliX` ）和類型的值表示 `Qubit` 。

下列作業是一個簡單的範例，它會在 $ \ket $ 狀態中配置一個 qubit {0} ，然後對它套用 Hadamard 作業 `H` 並測量結果 `PauliZ` 。

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

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

## <a name="borrowing-qubits-example"></a>借用 Qubits 範例

在 canon 中有使用關鍵字的範例 `borrowing` ，例如 `MultiControlledXBorrow` 以下定義的函數。
如果 `controls` 代表應新增至作業中的控制項 qubits `X` ，則 `Length(controls)-2` 此實作會加入許多中途 ancillas 的整體。

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

請注意，結合---的廣泛使用， `With` 其格式適用于支援 adjoint 的作業，也就是 `WithA` 在此範例中已進行---。
這是很好的程式設計風格，因為將控制項加入至包含的結構只會將 `With` 控制項傳播至內部作業。
此外，請注意，除了作業的 `body` 之外，也會 `controlled` 明確提供作業主體的執行，而不是使用 `controlled auto` 語句。
這是因為我們從線路的結構得知如何輕鬆加入進一步的控制項，相較于將控制項加入至中的每個和每個個別的閘道 `body` 。 

比較這段程式碼與另一個 canon 函式是有意義的，它會 `MultiControlledXClean` 達到相同的目標來執行乘以控制的作業 `X` ，不過，它使用了使用機制的幾個乾淨 qubits `using` 。 

## <a name="whats-next"></a>下一步
瞭解 Q # 中的[控制流程](xref:microsoft.quantum.guide.controlflow)。