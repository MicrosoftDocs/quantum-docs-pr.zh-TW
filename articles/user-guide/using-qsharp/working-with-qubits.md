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
# <a name="working-with-qubits"></a><span data-ttu-id="e21e6-103">使用量子位元</span><span class="sxs-lookup"><span data-stu-id="e21e6-103">Working with qubits</span></span>

<span data-ttu-id="e21e6-104">現在看過各種不同的 Q # 語言部分，讓我們深入瞭解，並瞭解如何使用 qubits 本身。</span><span class="sxs-lookup"><span data-stu-id="e21e6-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

<span data-ttu-id="e21e6-105">請注意，函式的主體中不允許任何這些語句。</span><span class="sxs-lookup"><span data-stu-id="e21e6-105">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="e21e6-106">只有在作業內才有效。</span><span class="sxs-lookup"><span data-stu-id="e21e6-106">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="e21e6-107">配置 Qubits</span><span class="sxs-lookup"><span data-stu-id="e21e6-107">Allocating Qubits</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="e21e6-108">清除 qubits</span><span class="sxs-lookup"><span data-stu-id="e21e6-108">Clean qubits</span></span>

<span data-ttu-id="e21e6-109">`using`語句是用來*配置*新的 qubits，以便在語句區塊期間使用。</span><span class="sxs-lookup"><span data-stu-id="e21e6-109">The `using` statement is used to *allocate* new qubits for use during a statement block.</span></span>

<span data-ttu-id="e21e6-110">語句包含關鍵字 `using` ，後面接著左括弧、系結 `(` 、右括弧 `)` 和語句區塊，可在其中使用 qubits。</span><span class="sxs-lookup"><span data-stu-id="e21e6-110">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="e21e6-111">系結遵循與語句相同的模式 `let` ：單一符號或符號的元組，後面接著等號 `=` ，以及單一值或相符的*初始化運算式*元組。</span><span class="sxs-lookup"><span data-stu-id="e21e6-111">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="e21e6-112">初始化運算式適用于單一 qubit，表示為 `Qubit()` ，或 qubits 的陣列， `Qubit[n]` 其中 `n` 是 `Int` 運算式。</span><span class="sxs-lookup"><span data-stu-id="e21e6-112">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="e21e6-113">例如，</span><span class="sxs-lookup"><span data-stu-id="e21e6-113">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="e21e6-114">以這種方式配置的任何 qubits 從 $ \ket {0} $ 狀態開始，在上述範例中， `register` 會在 state $ \ket {00000} = \ket \otimes \ket \otimes \cdots \otimes {0} {0} \ket $ 中啟動 {0} 。</span><span class="sxs-lookup"><span data-stu-id="e21e6-114">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="e21e6-115">在區塊結尾時 `using` ，該區塊所配置的任何 qubits 都會立即解除配置，而且無法再使用。</span><span class="sxs-lookup"><span data-stu-id="e21e6-115">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="e21e6-116">目的機器預期 qubits 在 {0} 解除配置之前會立即處於 $ \ket $ 狀態，以便可以重複使用並提供給其他 `using` 區塊進行配置。</span><span class="sxs-lookup"><span data-stu-id="e21e6-116">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="e21e6-117">可能的話，請使用單一作業將任何已配置的 qubits 傳回到 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="e21e6-117">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="e21e6-118">如果需要，您 @"microsoft.quantum.intrinsic.reset" 可以使用作業來測量 qubit，並使用該測量結果來確保測量的 qubit 會傳回 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="e21e6-118">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="e21e6-119">這類測量會摧毀具有剩餘 qubits 的任何會任何牽連，因此會影響計算。</span><span class="sxs-lookup"><span data-stu-id="e21e6-119">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="e21e6-120">借用的 Qubits</span><span class="sxs-lookup"><span data-stu-id="e21e6-120">Borrowed Qubits</span></span>

<span data-ttu-id="e21e6-121">`borrowing`語句是用來讓 qubits 可供暫時使用，而不需要處於特定狀態。</span><span class="sxs-lookup"><span data-stu-id="e21e6-121">The `borrowing` statement is used to make qubits available for temporary use, which do not need be in a specific state.</span></span>

<span data-ttu-id="e21e6-122">「借款」機制可讓您配置 qubits，在計算期間用來做為臨時空間。</span><span class="sxs-lookup"><span data-stu-id="e21e6-122">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span>
<span data-ttu-id="e21e6-123">這些 qubits 通常不是處於乾淨狀態，也就是說，它們不一定會在已知狀態中初始化，例如 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="e21e6-123">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="e21e6-124">這些通常稱為「已變更」 qubits，因為它們的狀態是未知的，甚至可以與量子電腦記憶體的其他部分光子。</span><span class="sxs-lookup"><span data-stu-id="e21e6-124">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="e21e6-125">系結會遵循與語句中的相同模式和規則 `using` 。</span><span class="sxs-lookup"><span data-stu-id="e21e6-125">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>
<span data-ttu-id="e21e6-126">例如，</span><span class="sxs-lookup"><span data-stu-id="e21e6-126">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="e21e6-127">借用的 qubits 處於不明狀態，超出語句區塊結尾的範圍。</span><span class="sxs-lookup"><span data-stu-id="e21e6-127">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="e21e6-128">借方會認可，使 qubits 處於借用時的相同狀態，也就是其在語句區塊開頭和結尾的狀態應該是相同的。</span><span class="sxs-lookup"><span data-stu-id="e21e6-128">The borrower commits to leaving the qubits in the same state they were in when they were borrowed,  i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="e21e6-129">此狀態特別不一定是傳統狀態，因此在大部分情況下，借用範圍不應包含測量。</span><span class="sxs-lookup"><span data-stu-id="e21e6-129">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="e21e6-130">當借用 qubits 時，系統會先嘗試從使用中的 qubits 填入要求，但不會在語句主體期間存取 `borrowing` 。</span><span class="sxs-lookup"><span data-stu-id="e21e6-130">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="e21e6-131">如果沒有足夠的 qubits，則會配置新的 qubits 來完成要求。</span><span class="sxs-lookup"><span data-stu-id="e21e6-131">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>


<span data-ttu-id="e21e6-132">在已變更 qubits 的已知使用案例中，是多個受控制 CNOT-CONTAINS 閘道的實作為，只需要極少的 qubits 和 incrementers。</span><span class="sxs-lookup"><span data-stu-id="e21e6-132">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="e21e6-133">請參閱下列[借用 Qubits 範例](#borrowing-qubits-example)，以查看在 Q # 中使用的範例，或[*使用具有以 Toffoli 為基礎之模組化乘法*](https://arxiv.org/abs/1611.07995)（Haner、Roetteler 和 Svore 2017）的 Qubits，針對利用借用 Qubits 的演算法來進行檔的分解。</span><span class="sxs-lookup"><span data-stu-id="e21e6-133">See the [Borrowing Qubits Example](#borrowing-qubits-example) below to see an example of their use in Q#, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>


## <a name="intrinsic-operations"></a><span data-ttu-id="e21e6-134">內部作業</span><span class="sxs-lookup"><span data-stu-id="e21e6-134">Intrinsic Operations</span></span>

<span data-ttu-id="e21e6-135">一旦配置之後，就可以將 qubit 傳遞至函數和作業。</span><span class="sxs-lookup"><span data-stu-id="e21e6-135">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="e21e6-136">在某種意義上，這就是問 # 程式可以使用 qubit 執行的動作，因為可以採取的動作全都定義為作業。</span><span class="sxs-lookup"><span data-stu-id="e21e6-136">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="e21e6-137">我們會在內建[作業和](xref:microsoft.quantum.libraries.standard.prelude)函式中更詳細地看到這些作業，但目前我們提到一些可用來與 qubits 互動的實用作業。</span><span class="sxs-lookup"><span data-stu-id="e21e6-137">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="e21e6-138">首先，單一 qubit 的 Pauli 運算子 $X $、$Y $ 和 $Z $ 會由內部作業（和）以 Q # 表示，而 `X` `Y` `Z` 每一個都有類型 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="e21e6-138">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="e21e6-139">如[內部作業和](xref:microsoft.quantum.libraries.standard.prelude)函式中所述，我們可以將 $X $ 和， `X` 視為不使用閘道的運算。</span><span class="sxs-lookup"><span data-stu-id="e21e6-139">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="e21e6-140">此作業 `X` 可讓我們針對某些傳統位字串 $s $，準備表單 $ \ket{s_0 s_1 \dots .. s_n} $ 的狀態：</span><span class="sxs-lookup"><span data-stu-id="e21e6-140">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="e21e6-141">之後，我們會看到更精簡的方式來撰寫此作業，而不需要手動進行流量控制。</span><span class="sxs-lookup"><span data-stu-id="e21e6-141">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="e21e6-142">我們也可以使用 \Right 轉換 $H $ 來準備狀態，例如 $ \ket{+} = \left （\ket {0} + \ket {1} \sqrt）/\ket {2} $ and $ \left {-} = \ket （\ket {0} -\right {1} \sqrt）/Hadamard {2} $，方法是透過內部作業，在 Q # 中表示 `H : (Qubit => Unit is Adj + Ctl)` ：</span><span class="sxs-lookup"><span data-stu-id="e21e6-142">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="e21e6-143">量測</span><span class="sxs-lookup"><span data-stu-id="e21e6-143">Measurements</span></span>

<span data-ttu-id="e21e6-144">使用作業 `Measure` ，這是內建的內建函式非單一作業，我們可以從類型的物件中提取傳統資訊， `Qubit` 並指派傳統值做為結果（具有保留類型 `Result` ），表示結果不再是配量狀態。</span><span class="sxs-lookup"><span data-stu-id="e21e6-144">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="e21e6-145">的輸入 `Measure` 是 Bloch 球體上的 Pauli 軸，以類型的值 `Pauli` （例如 `PauliX` ）和類型的值表示 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="e21e6-145">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="e21e6-146">下列作業是一個簡單的範例，它會在 $ \ket $ 狀態中配置一個 qubit {0} ，然後對它套用 Hadamard 作業 `H` 並測量結果 `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="e21e6-146">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="e21e6-147">下列作業會提供稍微較複雜的範例，如果類型的暫存器中的 `true` 所有 qubits 在以 `Qubit[]` 指定的 Pauli 為基礎進行測量時，則會傳回布林值，否則會傳回 `false` 。</span><span class="sxs-lookup"><span data-stu-id="e21e6-147">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

## <a name="borrowing-qubits-example"></a><span data-ttu-id="e21e6-148">借用 Qubits 範例</span><span class="sxs-lookup"><span data-stu-id="e21e6-148">Borrowing Qubits Example</span></span>

<span data-ttu-id="e21e6-149">在 canon 中有使用關鍵字的範例 `borrowing` ，例如 `MultiControlledXBorrow` 以下定義的函數。</span><span class="sxs-lookup"><span data-stu-id="e21e6-149">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="e21e6-150">如果 `controls` 代表應新增至作業中的控制項 qubits `X` ，則 `Length(controls)-2` 此實作會加入許多中途 ancillas 的整體。</span><span class="sxs-lookup"><span data-stu-id="e21e6-150">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="e21e6-151">請注意，結合---的廣泛使用， `With` 其格式適用于支援 adjoint 的作業，也就是 `WithA` 在此範例中已進行---。</span><span class="sxs-lookup"><span data-stu-id="e21e6-151">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example.</span></span>
<span data-ttu-id="e21e6-152">這是很好的程式設計風格，因為將控制項加入至包含的結構只會將 `With` 控制項傳播至內部作業。</span><span class="sxs-lookup"><span data-stu-id="e21e6-152">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="e21e6-153">此外，請注意，除了作業的 `body` 之外，也會 `controlled` 明確提供作業主體的執行，而不是使用 `controlled auto` 語句。</span><span class="sxs-lookup"><span data-stu-id="e21e6-153">Further, note that here in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="e21e6-154">這是因為我們從線路的結構得知如何輕鬆加入進一步的控制項，相較于將控制項加入至中的每個和每個個別的閘道 `body` 。</span><span class="sxs-lookup"><span data-stu-id="e21e6-154">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="e21e6-155">比較這段程式碼與另一個 canon 函式是有意義的，它會 `MultiControlledXClean` 達到相同的目標來執行乘以控制的作業 `X` ，不過，它使用了使用機制的幾個乾淨 qubits `using` 。</span><span class="sxs-lookup"><span data-stu-id="e21e6-155">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="whats-next"></a><span data-ttu-id="e21e6-156">下一步</span><span class="sxs-lookup"><span data-stu-id="e21e6-156">What's Next?</span></span>
<span data-ttu-id="e21e6-157">瞭解 Q # 中的[控制流程](xref:microsoft.quantum.guide.controlflow)。</span><span class="sxs-lookup"><span data-stu-id="e21e6-157">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>