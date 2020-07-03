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
# <a name="working-with-qubits"></a><span data-ttu-id="925c6-103">使用量子位元</span><span class="sxs-lookup"><span data-stu-id="925c6-103">Working with qubits</span></span>

<span data-ttu-id="925c6-104">Qubits 是量子運算中資訊的基本物件。</span><span class="sxs-lookup"><span data-stu-id="925c6-104">Qubits are the fundamental object of information in quantum computing.</span></span> <span data-ttu-id="925c6-105">如需 qubits 的一般簡介，請參閱瞭解配量[計算](xref:microsoft.quantum.overview.understanding)，若要深入瞭解其數學表示，請參閱[Qubit](xref:microsoft.quantum.concepts.qubit)。</span><span class="sxs-lookup"><span data-stu-id="925c6-105">For a general introduction to qubits, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), and to dive deeper into their mathematical representation, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span> 

<span data-ttu-id="925c6-106">本文將探討如何在 Q # 程式中使用和處理 qubits。</span><span class="sxs-lookup"><span data-stu-id="925c6-106">This article explores how to use and work with qubits in a Q# program.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="925c6-107">本文中所討論的語句都不是在函式主體內有效。</span><span class="sxs-lookup"><span data-stu-id="925c6-107">None of the statements discussed in this article are valid within the body of a function.</span></span> <span data-ttu-id="925c6-108">只有在作業內才有效。</span><span class="sxs-lookup"><span data-stu-id="925c6-108">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="925c6-109">配置 Qubits</span><span class="sxs-lookup"><span data-stu-id="925c6-109">Allocating Qubits</span></span>

<span data-ttu-id="925c6-110">因為實體 qubits 在量子電腦中是寶貴的資源，所以編譯器作業的一部分是要確保它們能夠盡可能有效率地使用。</span><span class="sxs-lookup"><span data-stu-id="925c6-110">Because physical qubits are a precious resource in a quantum computer, part of the compiler's job is to make sure they are being used as efficiently as possible.</span></span>
<span data-ttu-id="925c6-111">因此，您需要指示 Q # 來*配置*qubits，以便在特定的語句區塊中使用。</span><span class="sxs-lookup"><span data-stu-id="925c6-111">As such, you need to tell Q# to *allocate* qubits for use within a particular statement block.</span></span>
<span data-ttu-id="925c6-112">您可以將 qubits 配置為單一 qubit，或做為 qubits 的陣列（稱為暫存器 *）。*</span><span class="sxs-lookup"><span data-stu-id="925c6-112">You can allocate qubits as a single qubit, or as an array of qubits, known as a *register*.</span></span> 

### <a name="clean-qubits"></a><span data-ttu-id="925c6-113">清除 qubits</span><span class="sxs-lookup"><span data-stu-id="925c6-113">Clean qubits</span></span>

<span data-ttu-id="925c6-114">使用 `using` 語句來配置新的 qubits，以便在語句區塊期間使用。</span><span class="sxs-lookup"><span data-stu-id="925c6-114">Use the `using` statement to allocate new qubits for use during a statement block.</span></span>

<span data-ttu-id="925c6-115">語句包含關鍵字 `using` ，後面接著以括弧括住的系結 `( )` ，以及 qubits 可用的語句區塊。</span><span class="sxs-lookup"><span data-stu-id="925c6-115">The statement consists of the keyword `using`, followed by a binding enclosed in parentheses `( )` and the statement block within which the qubits are available.</span></span>
<span data-ttu-id="925c6-116">系結遵循與語句相同的模式 `let` ：單一符號或符號的元組，後面接著等號 `=` ，以及單一值或相符的*初始化運算式*元組。</span><span class="sxs-lookup"><span data-stu-id="925c6-116">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="925c6-117">初始化運算式適用于單一 qubit，表示為 `Qubit()` ，或 qubits 的陣列， `Qubit[n]` 其中 `n` 是 `Int` 運算式。</span><span class="sxs-lookup"><span data-stu-id="925c6-117">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="925c6-118">例如，</span><span class="sxs-lookup"><span data-stu-id="925c6-118">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="925c6-119">以這種方式配置的任何 qubits 從 $ \ket {0} $ 狀態開始。</span><span class="sxs-lookup"><span data-stu-id="925c6-119">Any qubits allocated in this way start off in the $\ket{0}$ state.</span></span> <span data-ttu-id="925c6-120">因此，在上一個範例中， `auxiliary` 是 state $ \ket $ 的單一 qubit {0} ，而且 `register` 是在五個 qubit 狀態 $ \ket = \ket \otimes \ket \otimes \cdots \otimes {00000} {0} {0} \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="925c6-120">Thus in the previous example, `auxiliary` is a single qubit in the state $\ket{0}$, and `register` is in the five-qubit state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="925c6-121">在區塊結尾時 `using` ，該區塊所配置的任何 qubits 都會立即解除配置，而且無法再使用。</span><span class="sxs-lookup"><span data-stu-id="925c6-121">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="925c6-122">目的機器可以重複使用已解除配置的 qubits，並將其提供給其他 `using` 區塊進行配置。</span><span class="sxs-lookup"><span data-stu-id="925c6-122">Target machines can reuse deallocated qubits and offer them to other `using` blocks for allocation.</span></span> <span data-ttu-id="925c6-123">因此，目的電腦預期 qubits 在 {0} 解除配置之前會立即處於 $ \ket $ 狀態。</span><span class="sxs-lookup"><span data-stu-id="925c6-123">As such, the target machine expects that qubits are in the $\ket{0}$ state immediately before deallocation.</span></span>
> <span data-ttu-id="925c6-124">可能的話，請使用單一作業將任何已配置的 qubits 傳回到 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="925c6-124">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="925c6-125">如果需要，您可以使用作業，此作業會藉 @"microsoft.quantum.intrinsic.reset" 由測量來將 qubit 傳回 $ \ket {0} $，並根據結果有條件地執行作業。</span><span class="sxs-lookup"><span data-stu-id="925c6-125">If need be, you can use the @"microsoft.quantum.intrinsic.reset" operation, which returns the qubit to $\ket{0}$ by measuring it and conditionally performing an operation based on the result.</span></span> <span data-ttu-id="925c6-126">這類量測會損毀具有剩餘 qubits 的任何會任何牽連，因而影響計算。</span><span class="sxs-lookup"><span data-stu-id="925c6-126">Such a measurement destroys any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="925c6-127">借用的 Qubits</span><span class="sxs-lookup"><span data-stu-id="925c6-127">Borrowed Qubits</span></span>

<span data-ttu-id="925c6-128">使用 `borrowing` 語句來配置 qubits 以供暫時使用，而不需要處於特定狀態。</span><span class="sxs-lookup"><span data-stu-id="925c6-128">Use the `borrowing` statement to allocate qubits for temporary use, which do not need to be in a specific state.</span></span>

<span data-ttu-id="925c6-129">在計算期間，您可以使用借用的 qubits 作為臨時空間。</span><span class="sxs-lookup"><span data-stu-id="925c6-129">You can use borrowed qubits as scratch space during a computation.</span></span>
<span data-ttu-id="925c6-130">這些 qubits 通常不是處於乾淨狀態，也就是說，它們不一定會在已知狀態中初始化，例如 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="925c6-130">These qubits are generally not in a clean state, that is, they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="925c6-131">這些通常稱為「已變更」 qubits，因為它們的狀態是未知的，甚至可以與量子電腦記憶體的其他部分光子。</span><span class="sxs-lookup"><span data-stu-id="925c6-131">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="925c6-132">系結遵循與語句相同的模式和規則 `using` 。</span><span class="sxs-lookup"><span data-stu-id="925c6-132">The binding follows the same pattern and rules as the `using` statement.</span></span>
<span data-ttu-id="925c6-133">例如，</span><span class="sxs-lookup"><span data-stu-id="925c6-133">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="925c6-134">借用的 qubits 處於不明狀態，超出語句區塊結尾的範圍。</span><span class="sxs-lookup"><span data-stu-id="925c6-134">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="925c6-135">借方會認可，使 qubits 在其借用時處於相同的狀態;也就是說，在語句區塊的開頭和結尾的狀態應該相同。</span><span class="sxs-lookup"><span data-stu-id="925c6-135">The borrower commits to leaving the qubits in the same state they were in when they borrowed them; that is, their state at the beginning and the end of the statement block should be the same.</span></span>
<span data-ttu-id="925c6-136">因為此狀態不一定是傳統狀態，所以在大部分的情況下，借用範圍都不應該包含度量。</span><span class="sxs-lookup"><span data-stu-id="925c6-136">Because this state is not necessarily a classical state, in most cases borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="925c6-137">當借用 qubits 時，系統會先嘗試從使用中的 qubits 填入要求，但不會在語句主體期間存取 `borrowing` 。</span><span class="sxs-lookup"><span data-stu-id="925c6-137">When borrowing qubits, the system first tries to fill the request from qubits that are in use but not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="925c6-138">如果沒有足夠的 qubits，則會配置新的 qubits 來完成要求。</span><span class="sxs-lookup"><span data-stu-id="925c6-138">If there aren't enough such qubits, then it allocates new qubits to complete the request.</span></span>

<span data-ttu-id="925c6-139">在已變更 qubits 的已知使用案例中，是多個受控制 CNOT-CONTAINS 閘道的實作為，只需要極少的 qubits 和 incrementers。</span><span class="sxs-lookup"><span data-stu-id="925c6-139">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="925c6-140">如需如何在 Q # 中使用的範例，請參閱本文章中的[借用 Qubits 範例](#borrowing-qubits-example)，或[*使用具有以 Toffoli 為基礎之模組化乘法*](https://arxiv.org/abs/1611.07995)（Haner、Roetteler 和 Svore 2017）的 Qubits 的檔，以取得利用借用 Qubits 的演算法。</span><span class="sxs-lookup"><span data-stu-id="925c6-140">For an example of their use in Q#, see [Borrowing Qubits Example](#borrowing-qubits-example) in this article, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="925c6-141">內部作業</span><span class="sxs-lookup"><span data-stu-id="925c6-141">Intrinsic Operations</span></span>

<span data-ttu-id="925c6-142">一旦配置之後，您就可以將 qubit 傳遞至函數和作業。</span><span class="sxs-lookup"><span data-stu-id="925c6-142">Once allocated, you can pass a qubit to functions and operations.</span></span>
<span data-ttu-id="925c6-143">在某種意義上，這就是問 # 程式可以使用 qubit 執行的動作，因為可以採取的動作全都定義為作業。</span><span class="sxs-lookup"><span data-stu-id="925c6-143">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>

<span data-ttu-id="925c6-144">本文討論幾個實用的 Q # 作業，可讓您用來與 qubits 互動。</span><span class="sxs-lookup"><span data-stu-id="925c6-144">This article discusses a few useful Q# operations that you can use to interact with qubits.</span></span>
<span data-ttu-id="925c6-145">如需這些和其他專案的詳細資訊，請參閱[內部作業和函數](xref:microsoft.quantum.libraries.standard.prelude)。</span><span class="sxs-lookup"><span data-stu-id="925c6-145">For more detail about these and others, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span> 

<span data-ttu-id="925c6-146">首先，單一 qubit 的 Pauli 運算子 $X $、$Y $ 和 $Z $ 會由內部作業（和）以 Q # 表示，而 [`X`](xref:microsoft.quantum.intrinsic.x) [`Y`](xref:microsoft.quantum.intrinsic.y) [`Z`](xref:microsoft.quantum.intrinsic.z) 每一個都有類型 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="925c6-146">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations [`X`](xref:microsoft.quantum.intrinsic.x), [`Y`](xref:microsoft.quantum.intrinsic.y), and [`Z`](xref:microsoft.quantum.intrinsic.z), each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="925c6-147">如[內部作業和](xref:microsoft.quantum.libraries.standard.prelude)函式中所述，請將 $X $，而 `X` 不是閘道。</span><span class="sxs-lookup"><span data-stu-id="925c6-147">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="925c6-148">您可以使用作業 `X` 來準備 s_1 \dots .. s_n} $ 格式的 s_0 的狀態，以取得某些傳統位字串 $s $：</span><span class="sxs-lookup"><span data-stu-id="925c6-148">You can use the `X` operation to prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="925c6-149">稍後，您將會看到更精簡的方式來撰寫此作業，而不需要手動控制流程。</span><span class="sxs-lookup"><span data-stu-id="925c6-149">Later, you will see more compact ways of writing this operation that do not require manual control flow.</span></span>

<span data-ttu-id="925c6-150">您也可以使用 \Right 轉換 $H $ 來準備狀態，例如 $ \ket{+} = \left （\ket {0} + \ket {1} \sqrt）/\ket {2} $ 和 $ \left {-} = \ket （\ket {0} -\right {1} \sqrt）/Hadamard {2} $，方法是透過內建作業 [`H`](xref:microsoft.quantum.intrinsic.h) （也屬於類型（Qubit => 單位為形容詞 + Ctl））在 Q # 中表示）：</span><span class="sxs-lookup"><span data-stu-id="925c6-150">You can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation [`H`](xref:microsoft.quantum.intrinsic.h) (also of type (Qubit => Unit is Adj + Ctl)\`):</span></span>

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

## <a name="measurements"></a><span data-ttu-id="925c6-151">量測</span><span class="sxs-lookup"><span data-stu-id="925c6-151">Measurements</span></span>

<span data-ttu-id="925c6-152">個別 qubits 的測量可以用不同的基底執行，每個都是由[Bloch 球體](xref:microsoft.quantum.glossary#bloch-sphere)上的 Pauli 軸表示。</span><span class="sxs-lookup"><span data-stu-id="925c6-152">Measurements of individual qubits can be performed in different bases, each represented by a Pauli axis on the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere).</span></span>
<span data-ttu-id="925c6-153">*計算基礎*是指 `PauliZ` 基礎，而且是用於測量的最常見基礎。</span><span class="sxs-lookup"><span data-stu-id="925c6-153">The *computational basis* refers to the `PauliZ` basis, and is the most common basis used for measurement.</span></span>

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a><span data-ttu-id="925c6-154">以基礎測量單一 qubit `PauliZ`</span><span class="sxs-lookup"><span data-stu-id="925c6-154">Measure a single qubit in the `PauliZ` basis</span></span>

<span data-ttu-id="925c6-155">使用作業 [`M`](xref:microsoft.quantum.intrinsic.m) ，這是內建的內建函式非單一作業，可依基礎測量單一 qubit， `PauliZ` 並將傳統值指派給結果。</span><span class="sxs-lookup"><span data-stu-id="925c6-155">Use the [`M`](xref:microsoft.quantum.intrinsic.m) operation, which is a built-in intrinsic non-unitary operation, to measure a single qubit in the `PauliZ` basis and assign a classical value to the result.</span></span>
<span data-ttu-id="925c6-156">`M`具有保留的傳回類型， `Result` 它只能接受值 `Zero` 或 `One` 對應至測量的狀態 $ \ket {0} $ 或 $ \ket {1} $-表示結果不再是配量狀態。</span><span class="sxs-lookup"><span data-stu-id="925c6-156">`M` has a reserved return type, `Result`, which can only take values `Zero` or `One` corresponding to the measured states $\ket{0}$ or $\ket{1}$ - indicating that the result is no longer a quantum state.</span></span>

<span data-ttu-id="925c6-157">下列作業是一個簡單的範例，它會在 $ \ket $ 狀態中配置一個 qubit {0} ，然後對它套用 Hadamard 作業 `H` 並測量結果 `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="925c6-157">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

### <a name="measure-one-or-more-qubits-in-specific-bases"></a><span data-ttu-id="925c6-158">測量特定基底中的一或多個 qubits</span><span class="sxs-lookup"><span data-stu-id="925c6-158">Measure one or more qubits in specific bases</span></span>

<span data-ttu-id="925c6-159">若要測量特定基底中一個或多個 qubits 的陣列，您可以使用作業 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 。</span><span class="sxs-lookup"><span data-stu-id="925c6-159">To measure an array of one or more qubits in specific bases, you can use the [`Measure`](xref:microsoft.quantum.intrinsic.measure) operation.</span></span>

<span data-ttu-id="925c6-160">的輸入 `Measure` 是類型的陣列 `Pauli` （例如）， `[PauliX, PauliZ, PauliZ]` 以及 qubits 的陣列。</span><span class="sxs-lookup"><span data-stu-id="925c6-160">The inputs to `Measure` are an array of `Pauli` types (for example, `[PauliX, PauliZ, PauliZ]`) and an array of qubits.</span></span>

<span data-ttu-id="925c6-161">下列作業會提供稍微較複雜的範例，如果類型的暫存器中的 `true` 所有 qubits 在以 `Qubit[]` 指定的 Pauli 為基礎進行測量時，則會傳回布林值，否則會傳回 `false` 。</span><span class="sxs-lookup"><span data-stu-id="925c6-161">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="925c6-162">請注意，此範例 `Measure` 一次只會在個別的 qubits 上執行，但作業可以延伸到多個 qubits 的聯合測量。</span><span class="sxs-lookup"><span data-stu-id="925c6-162">Note that this example still only performs `Measure` on individual qubits one at a time, but the operation can be extended to joint measurements on multiple qubits.</span></span>

## <a name="borrowing-qubits-example"></a><span data-ttu-id="925c6-163">借用 Qubits 範例</span><span class="sxs-lookup"><span data-stu-id="925c6-163">Borrowing Qubits Example</span></span>

<span data-ttu-id="925c6-164">Canon 中有一些使用關鍵字的範例 `borrowing` ，例如下列函數 `MultiControlledXBorrow` 。</span><span class="sxs-lookup"><span data-stu-id="925c6-164">There are examples in the canon that use the `borrowing` keyword, such as the following function `MultiControlledXBorrow`.</span></span> <span data-ttu-id="925c6-165">如果 `controls` 代表要加入至作業的控制項 qubits `X` ，則此實作為新增的已變更[ancillas](xref:microsoft.quantum.glossary#ancilla)數目為 `Length(controls)-2` 。</span><span class="sxs-lookup"><span data-stu-id="925c6-165">If `controls` denotes the control qubits to add to an `X` operation, then the number of dirty [ancillas](xref:microsoft.quantum.glossary#ancilla) added by this implementation is `Length(controls)-2`.</span></span>

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

<span data-ttu-id="925c6-166">請注意，此範例使用結合的廣泛用法 `With` ，其格式適用于支援 adjoint 的作業，例如 `WithA` 。</span><span class="sxs-lookup"><span data-stu-id="925c6-166">Note that this example used extensive use of the `With` combinator, in its form that is applicable for operations that support adjoint, for example, `WithA`.</span></span>
<span data-ttu-id="925c6-167">這是很好的程式設計風格，因為將控制項加入至包含的結構只會將 `With` 控制項傳播至內部作業。</span><span class="sxs-lookup"><span data-stu-id="925c6-167">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="925c6-168">另請注意，除了作業的 `body` 之外，也會 `controlled` 明確提供作業主體的執行，而不是使用 `controlled auto` 語句。</span><span class="sxs-lookup"><span data-stu-id="925c6-168">Also note that, in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="925c6-169">原因是，因為線路的結構，所以您可以輕鬆地加入進一步的控制項，相較于將控制項加入至中的每個閘道，這是很有説明的 `body` 。</span><span class="sxs-lookup"><span data-stu-id="925c6-169">The reason for this is that, because of the structure of the circuit, it is easy to add further controls, which is beneficial compared to adding control to each gate in the `body`.</span></span> 

<span data-ttu-id="925c6-170">比較這段程式碼與另一個 canon 函式是有意義的，它會 `MultiControlledXClean` 達到相同的目標來執行乘以控制的作業 `X` ，不過，它使用了使用機制的幾個乾淨 qubits `using` 。</span><span class="sxs-lookup"><span data-stu-id="925c6-170">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="925c6-171">接下來的步驟</span><span class="sxs-lookup"><span data-stu-id="925c6-171">Next steps</span></span>

<span data-ttu-id="925c6-172">瞭解 Q # 中的[控制流程](xref:microsoft.quantum.guide.controlflow)。</span><span class="sxs-lookup"><span data-stu-id="925c6-172">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>