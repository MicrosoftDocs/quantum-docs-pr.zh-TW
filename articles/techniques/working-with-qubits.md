---
title: 使用 Qubits
description: 瞭解如何配置 qubits、在作業和函式中使用它們，以及測量結果。
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 1aa2432996dda61d099e3b5bb4db78379ce43d97
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907642"
---
# <a name="working-with-qubits"></a><span data-ttu-id="daa22-103">使用 Qubits</span><span class="sxs-lookup"><span data-stu-id="daa22-103">Working with Qubits</span></span>

<span data-ttu-id="daa22-104">現在看過各種不同的 Q # 語言部分，讓我們深入瞭解，並瞭解如何使用 qubits 本身。</span><span class="sxs-lookup"><span data-stu-id="daa22-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="daa22-105">配置 Qubits</span><span class="sxs-lookup"><span data-stu-id="daa22-105">Allocating Qubits</span></span>

<span data-ttu-id="daa22-106">首先，若要取得可在 Q # 中使用的 qubit，我們會在 `using` 區塊內*配置*qubits：</span><span class="sxs-lookup"><span data-stu-id="daa22-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="daa22-107">以這種方式配置的任何 qubits 都會從 $ \ket{0}$ state 開始，在上述範例中，`register` 是在 state $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$。</span><span class="sxs-lookup"><span data-stu-id="daa22-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="daa22-108">在 `using` 區塊的結尾，該區塊配置的任何 qubits 都會立即解除配置，而且無法再使用。</span><span class="sxs-lookup"><span data-stu-id="daa22-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="daa22-109">目的電腦預期 qubits 會在解除配置之前立即處於 $ \ket{0}$ 狀態，以便可重複使用並提供給其他 `using` 區塊進行配置。</span><span class="sxs-lookup"><span data-stu-id="daa22-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="daa22-110">可能的話，請使用單一作業將任何配置的 qubits 傳回到 $ \ket{0}$。</span><span class="sxs-lookup"><span data-stu-id="daa22-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="daa22-111">如果需要，您可以使用 @"microsoft.quantum.intrinsic.reset" 作業來測量 qubit，並使用該測量結果來確保測量的 qubit 會傳回 $ \ket{0}$。</span><span class="sxs-lookup"><span data-stu-id="daa22-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="daa22-112">這類測量會摧毀具有剩餘 qubits 的任何會任何牽連，因此會影響計算。</span><span class="sxs-lookup"><span data-stu-id="daa22-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="daa22-113">內部作業</span><span class="sxs-lookup"><span data-stu-id="daa22-113">Intrinsic Operations</span></span>

<span data-ttu-id="daa22-114">一旦配置之後，就可以將 qubit 傳遞至函數和作業。</span><span class="sxs-lookup"><span data-stu-id="daa22-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="daa22-115">在某種意義上，這就是問 # 程式可以使用 qubit 執行的動作，因為可以採取的動作全都定義為作業。</span><span class="sxs-lookup"><span data-stu-id="daa22-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="daa22-116">我們會在內建[作業和](xref:microsoft.quantum.libraries.standard.prelude)函式中更詳細地看到這些作業，但目前我們提到一些可用來與 qubits 互動的實用作業。</span><span class="sxs-lookup"><span data-stu-id="daa22-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="daa22-117">首先，單一 qubit 的 Pauli 運算子 $X $、$Y $ 和 $Z $ 在 Q # 中是由內部作業 `X`、`Y`和 `Z`所表示，而每一個都有類型 `(Qubit => Unit is Adj + Ctl)`。</span><span class="sxs-lookup"><span data-stu-id="daa22-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="daa22-118">如[內部作業和](xref:microsoft.quantum.libraries.standard.prelude)函式中所述，我們可以將 $X $，而將 `X` 視為「位移」操作，而不是閘道。</span><span class="sxs-lookup"><span data-stu-id="daa22-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="daa22-119">`X` 作業可讓我們為一些傳統的位字串（$s $）準備格式為 $ \ket{s_0 s_1 \dots . s_n} $ 的狀態：</span><span class="sxs-lookup"><span data-stu-id="daa22-119">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="daa22-120">之後，我們會看到更精簡的方式來撰寫此作業，而不需要手動進行流量控制。</span><span class="sxs-lookup"><span data-stu-id="daa22-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="daa22-121">我們也可以使用 \Right 轉換{0} $ 來準備狀態，例如 $ \ket{+} = \left （\ket{0} + \ket{1}\sqrt）/\ket{2}$ 和 $ \left{-} = \ket （\ket{1}-\right{2}\sqrt）/Hadamard $H $，方法是 `H : (Qubit => Unit is Adj + Ctl)`：</span><span class="sxs-lookup"><span data-stu-id="daa22-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="daa22-122">量測</span><span class="sxs-lookup"><span data-stu-id="daa22-122">Measurements</span></span>

<span data-ttu-id="daa22-123">使用 `Measure` 作業，這是內建的內建函式非單一作業，我們可以從類型的物件中解壓縮傳統資訊 `Qubit` 並指派傳統值做為結果，其中具有保留類型 `Result`，表示結果不再是配量狀態。</span><span class="sxs-lookup"><span data-stu-id="daa22-123">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="daa22-124">`Measure` 的輸入是 Bloch 球體上的 Pauli 軸，以 `Pauli` 類型的值（例如 `PauliX`）和 `Qubit`類型的值來表示。</span><span class="sxs-lookup"><span data-stu-id="daa22-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="daa22-125">下列作業是一個簡單的範例，它會在 $ \ket{0}$ 狀態中配置一個 qubit，然後將 Hadamard 作業 `H` 套用至該作業，並以 `PauliZ` 為基礎來測量結果。</span><span class="sxs-lookup"><span data-stu-id="daa22-125">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="daa22-126">下列作業會提供稍微較複雜的範例，如果型別 `Qubit[]` 暫存器中的所有 qubits 都是以指定的 Pauli 為基礎來測量，則會傳回布林值 `true`，否則會傳回 `false`。</span><span class="sxs-lookup"><span data-stu-id="daa22-126">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="daa22-127">Q # 語言可讓傳統控制流程相依于測量 qubits 的結果。</span><span class="sxs-lookup"><span data-stu-id="daa22-127">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="daa22-128">這項功能可讓您執行功能強大的概率小工具，以降低執行 unitaries 的計算成本。</span><span class="sxs-lookup"><span data-stu-id="daa22-128">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="daa22-129">例如，在 Q # 中執行所謂的*重複-成功*（ru）模式是很容易的。</span><span class="sxs-lookup"><span data-stu-id="daa22-129">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="daa22-130">這些 ru 模式是概率的程式，在基本閘道方面具有*預期*的低成本，但真正的成本取決於實際執行，以及各種可能分支的實際交錯。</span><span class="sxs-lookup"><span data-stu-id="daa22-130">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="daa22-131">為了協助重複執行-成功（ru）模式，Q # 支援結構</span><span class="sxs-lookup"><span data-stu-id="daa22-131">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

<span data-ttu-id="daa22-132">其中 `statementBlock1` 和 `statementBlock2` 是零或多個 Q # 語句，並 `expression` 任何評估為類型 `Bool`值的有效運算式。</span><span class="sxs-lookup"><span data-stu-id="daa22-132">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="daa22-133">在典型的使用案例中，下列 Q # 作業會在 Bloch 球體上，針對 $ （I + 2i Z）/\sqrt{5}$ 的無理軸執行旋轉。</span><span class="sxs-lookup"><span data-stu-id="daa22-133">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="daa22-134">這是使用已知的 ru 模式來完成：</span><span class="sxs-lookup"><span data-stu-id="daa22-134">This is accomplished by using a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

<span data-ttu-id="daa22-135">這個範例示範如何使用可變動的變數 `finished` 這是在整個重複執行-修復迴圈的範圍內，而且會在迴圈之前初始化，並在修復步驟中更新。</span><span class="sxs-lookup"><span data-stu-id="daa22-135">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="daa22-136">最後，我們會顯示一個 ru 模式範例，以準備量子狀態 $ \frac{1}{\sqrt{3}} \left （\sqrt{2}\ket{0}+ \ket{1}\right） $，從 $ \ket{+} $ 狀態開始。</span><span class="sxs-lookup"><span data-stu-id="daa22-136">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="daa22-137">另請參閱[標準程式庫所提供的單元測試範例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)：</span><span class="sxs-lookup"><span data-stu-id="daa22-137">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="daa22-138">這項作業中所顯示的值得注意的程式設計功能，是更複雜的 `fixup` 部分的迴圈，這牽涉到配量作業，以及使用 `AssertProb` 的語句，來確定在程式的特定指定點測量量子狀態的機率。</span><span class="sxs-lookup"><span data-stu-id="daa22-138">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="daa22-139">如需[`Assert`](xref:microsoft.quantum.intrinsic.assert)和[`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob)作業的詳細資訊，請參閱[測試和調試](xref:microsoft.quantum.techniques.testing-and-debugging)程式。</span><span class="sxs-lookup"><span data-stu-id="daa22-139">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>
