---
title: 使用 Qubits |Microsoft Docs
description: 使用 Qubits
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 477b358c3eba58b62926b4e9094770c9741cac92
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864248"
---
# <a name="working-with-qubits"></a>使用 Qubits #

現在看過各種不同的 Q # 語言部分，讓我們深入瞭解，並瞭解如何使用 qubits 本身。

## <a name="allocating-qubits"></a>配置 Qubits ##

首先，若要取得可在 Q # 中使用的 qubit，我們會在 `using` 區塊內*配置*qubits：

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

以這種方式配置的任何 qubits 都會從 $ \ket{0}$ state 開始，在上述範例中，`register` 是在 state $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$。
在 `using` 區塊的結尾，該區塊配置的任何 qubits 都會立即解除配置，而且無法再使用。

> [!WARNING]
> 目的電腦預期 qubits 會在解除配置之前立即處於 $ \ket{0}$ 狀態，以便可重複使用並提供給其他 `using` 區塊進行配置。
> 可能的話，請使用單一作業將任何配置的 qubits 傳回到 $ \ket{0}$。
> 如果需要，您可以使用 @"microsoft.quantum.intrinsic.reset" 作業來測量 qubit，並使用該測量結果來確保測量的 qubit 會傳回 $ \ket{0}$。 這類測量會摧毀具有剩餘 qubits 的任何會任何牽連，因此會影響計算。 

## <a name="intrinsic-operations"></a>內部作業 ##

一旦配置之後，就可以將 qubit 傳遞至函數和作業。
在某種意義上，這就是問 # 程式可以使用 qubit 執行的動作，因為可以採取的動作全都定義為作業。
我們會在內建[作業和](xref:microsoft.quantum.libraries.standard.prelude)函式中更詳細地看到這些作業，但目前我們提到一些可用來與 qubits 互動的實用作業。

首先，單一 qubit 的 Pauli 運算子 $X $、$Y $ 和 $Z $ 在 Q # 中是由內部作業 `X`、`Y`和 `Z`所表示，而每一個都有類型 `(Qubit => Unit is Adj + Ctl)`。
如[內部作業和](xref:microsoft.quantum.libraries.standard.prelude)函式中所述，我們可以將 $X $，而將 `X` 視為「位移」操作，而不是閘道。
這可讓我們準備一些傳統位字串 $s $ 的格式 $ \ket{s_0 s_1 \dots . s_n} $ 的狀態：

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

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> 之後，我們會看到更精簡的方式來撰寫此作業，而不需要手動進行流量控制。

我們也可以使用 \Right 轉換{0} $ 來準備狀態，例如 $ \ket{+} = \left （\ket{0} + \ket{1}\sqrt）/\ket{2}$ 和 $ \left{-} = \ket （\ket{1}-\right{2}\sqrt）/Hadamard $H $，方法是 `H : (Qubit => Unit is Adj + Ctl)`：

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

## <a name="measurements"></a>度量 ##

使用 `Measure` 作業，這是內建的內建函式非單一作業，我們可以從類型的物件中提取傳統資訊 `Qubit` 並指派傳統值做為結果，其中具有保留類型 `Result`，表示結果不再是配量狀態。 `Measure` 的輸入是 Bloch 球體上的 Pauli 軸，以 `Pauli` 類型的物件（例如 `PauliX`）和 `Qubit`類型的物件表示。 

下列作業是一個簡單的範例，它會在 $ \ket{0}$ state 中建立一個 qubit，然後對它套用 Hadamard 閘道 ``H``，然後以 `PauliZ` 為基礎來測量結果。 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
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

下列作業會傳回一個稍微複雜的範例，如果類型為 `Qubit[]` 的暫存器中的所有 qubits 都在狀態為零，則會以指定的 Pauli 為基礎，並 `false` 以其他方式來測量，這會傳回布林值 `true`。 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

Q # 語言允許將傳統控制流程相依于 qubits 的測量結果。 這可讓執行功能強大的概率小工具，以降低執行 unitaries 的計算成本。 例如，您可以輕鬆地在 Q # 中執行所謂的*重複直到成功*，也就是在基本閘道方面具有*預期*低成本的概率線路，但真正的成本取決於實際執行，以及各種可能分支的實際交錯。 

為了協助重複執行-成功（ru）模式，Q # 支援結構
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
其中 `statementBlock1` 和 `statementBlock2` 是零或多個 Q # 語句，並 `expression` 任何評估為類型 `Bool`值的有效運算式。 在典型的使用案例中，下列電路會在 Bloch 球體上執行無理軸（I + 2i Z）/\sqrt{5}$ 周圍的旋轉。 這是使用已知的 ru 模式來完成： 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

這個範例示範如何使用可變動的變數 `finished` 這是在整個重複執行-修復迴圈的範圍內，而且會在迴圈之前初始化，並在修復步驟中更新。

最後，我們會顯示一個 ru 模式範例，以準備量子狀態 $ \frac{1}{\sqrt{3}} \left （\sqrt{2}\ket{0}+ \ket{1}\right） $，從 $ \ket{+} $ 狀態開始。 另請參閱[標準程式庫所提供的單元測試範例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)： 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
這項作業中所顯示的重要程式設計功能，是包含配量作業的迴圈中較複雜的 `fixup` 部分，以及使用 `AssertProb` 的語句，來確定在程式中特定點測量量子狀態的機率。 如需 `Assert` 和 `AssertProb` 語句的詳細資訊，請參閱[測試和調試](xref:microsoft.quantum.techniques.testing-and-debugging)程式。 
