---
title: 'Q # 標準程式庫中的診斷'
description: '瞭解用於在量副程式中攔截錯誤或錯誤的 Q # 標準程式庫中的診斷功能和作業。'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: fa5173f710dd9e0b0b2c110e45aa0bf019111aca
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274607"
---
# <a name="diagnostics"></a><span data-ttu-id="bda6b-103">診斷</span><span class="sxs-lookup"><span data-stu-id="bda6b-103">Diagnostics</span></span> #

<span data-ttu-id="bda6b-104">與傳統開發一樣，要能夠診斷量副程式中的錯誤和錯誤是很重要的。</span><span class="sxs-lookup"><span data-stu-id="bda6b-104">As with classical development, it is important to be able to diagnose mistakes and errors in quantum programs.</span></span>
<span data-ttu-id="bda6b-105">問 # 標準程式庫提供各種不同的方式來確保量副程式的正確性，如中所述 <xref:microsoft.quantum.guide.testingdebugging> 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-105">The Q# standard libraries provide a variety of different ways to ensure the correctness of quantum programs, as detailed in <xref:microsoft.quantum.guide.testingdebugging>.</span></span>
<span data-ttu-id="bda6b-106">大致上來說，這項支援是以函式和作業的形式提供，以指示目的電腦向主機程式或開發人員提供額外的診斷資訊，或是強制執行由函數或作業呼叫所表示的條件和非變異性的正確性。</span><span class="sxs-lookup"><span data-stu-id="bda6b-106">Largely speaking, this support comes in the form of functions and operations that either instruct the target machine to provide additional diagnostic information to the host program or developer, or enforce the correctness of conditions and invariants expressed by the function or operation call.</span></span>

## <a name="machine-diagnostics"></a><span data-ttu-id="bda6b-107">機器診斷</span><span class="sxs-lookup"><span data-stu-id="bda6b-107">Machine Diagnostics</span></span> ##

<span data-ttu-id="bda6b-108">您可以使用函 <xref:microsoft.quantum.intrinsic.message> 式，以電腦相依的方式來記錄訊息，以取得有關傳統值的診斷。</span><span class="sxs-lookup"><span data-stu-id="bda6b-108">Diagnostics about classical values can be obtained by using the <xref:microsoft.quantum.intrinsic.message> function to log a message in a machine-dependent way.</span></span>
<span data-ttu-id="bda6b-109">根據預設，這會將字串寫入主控台。</span><span class="sxs-lookup"><span data-stu-id="bda6b-109">By default, this writes the string to the console.</span></span>
<span data-ttu-id="bda6b-110">與字串插值一起使用， <xref:microsoft.quantum.intrinsic.message> 可讓您輕鬆地報告有關傳統值的診斷資訊：</span><span class="sxs-lookup"><span data-stu-id="bda6b-110">Used together with interpolated strings, <xref:microsoft.quantum.intrinsic.message> makes it easy to report diagnostic information about classical values:</span></span>

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> <span data-ttu-id="bda6b-111">`Message`具有簽章 `(String -> Unit)` ，再次表示無法從 Q # 中觀察發出的偵錯工具記錄訊息。</span><span class="sxs-lookup"><span data-stu-id="bda6b-111">`Message` has signature `(String -> Unit)`, again representing that emitting a debug log message cannot be observed from within Q#.</span></span>

<span data-ttu-id="bda6b-112"><xref:microsoft.quantum.diagnostics.dumpmachine>和 <xref:microsoft.quantum.diagnostics.dumpregister> callables 會指示目的電腦提供有關目前已配置之所有 qubits 的診斷資訊，或分別針對特定的 qubits 註冊。</span><span class="sxs-lookup"><span data-stu-id="bda6b-112">The <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister> callables instruct target machines to provide diagnostic information about all currently allocated qubits or about a specific register of qubits, respectively.</span></span>
<span data-ttu-id="bda6b-113">每一部目的電腦都會因回應傾印指令所提供的診斷資訊而有所不同。</span><span class="sxs-lookup"><span data-stu-id="bda6b-113">Each target machine varies in what diagnostic information is provided in response to a dump instruction.</span></span>
<span data-ttu-id="bda6b-114">例如，[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器目的機器會提供主機程式，其狀態向量會在內部用來代表 qubits 的暫存器。</span><span class="sxs-lookup"><span data-stu-id="bda6b-114">The [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) target machine, for instance, provides the host program with the state vector that it uses internally to represent a register of qubits.</span></span>
<span data-ttu-id="bda6b-115">相較之下， [Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)模擬器目的電腦會針對每個 qubit 提供單一的傳統位。</span><span class="sxs-lookup"><span data-stu-id="bda6b-115">By comparison, the [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator) target machine provides a single classical bit for each qubit.</span></span>

 <span data-ttu-id="bda6b-116">若要深入瞭解[完整狀態模擬器的](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` 輸出，請參閱[測試和調試](xref:microsoft.quantum.guide.testingdebugging#dump-functions)程式一文的傾印函式一節。</span><span class="sxs-lookup"><span data-stu-id="bda6b-116">To learn more about the [full state simulator's](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` output, take a look at the dump functions section of our [testing and debugging article](xref:microsoft.quantum.guide.testingdebugging#dump-functions).</span></span>


## <a name="facts-and-assertions"></a><span data-ttu-id="bda6b-117">事實和判斷提示</span><span class="sxs-lookup"><span data-stu-id="bda6b-117">Facts and Assertions</span></span> ##

<span data-ttu-id="bda6b-118">如[測試和](xref:microsoft.quantum.guide.testingdebugging)偵測中所述，簽章或的函式或作業會 `Unit -> Unit` `Unit => Unit` 分別標記為*單元測試*。</span><span class="sxs-lookup"><span data-stu-id="bda6b-118">As discussed in [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging), a function or operation with signature `Unit -> Unit` or `Unit => Unit`, respectively, can be marked as a *unit test*.</span></span>
<span data-ttu-id="bda6b-119">每個單元測試通常包含一個小型的配量程式，以及一個或多個檢查該程式正確性的條件。</span><span class="sxs-lookup"><span data-stu-id="bda6b-119">Each unit test generally consists of a small quantum program, along with one or more conditions that check the correctness of that program.</span></span>
<span data-ttu-id="bda6b-120">這些條件可以是_事實_的形式，它會檢查輸入的值，或_判斷_提示，檢查傳遞做為輸入的一個或多個 qubits 的狀態。</span><span class="sxs-lookup"><span data-stu-id="bda6b-120">These conditions can come in the form of either _facts_, which check the values of their inputs, or _assertions_, which check the states of one or more qubits passed as input.</span></span>

<span data-ttu-id="bda6b-121">例如， `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` 代表 $1 + 1 = $2 的數學事實，而則 `AssertQubit(One, qubit)` 表示測量 `qubit` 會傳回 `One` 具有確定性的條件。</span><span class="sxs-lookup"><span data-stu-id="bda6b-121">For example, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` represents the mathematical fact that $1 + 1 = 2$, while `AssertQubit(One, qubit)` represents the condition that measuring `qubit` will return a `One` with certainty.</span></span>
<span data-ttu-id="bda6b-122">在先前的案例中，我們可以檢查只指定其值的條件是否正確，而在後者中，我們必須知道 qubit 狀態的相關資訊，才能評估判斷提示。</span><span class="sxs-lookup"><span data-stu-id="bda6b-122">In the former case, we can check the correctness of the condition given only its values, while in the latter, we must know something about the state of the qubit in order to evaluate the assertion.</span></span>

<span data-ttu-id="bda6b-123">Q # 標準程式庫提供數個不同的函數來表示事實，包括：</span><span class="sxs-lookup"><span data-stu-id="bda6b-123">The Q# standard libraries provide several different functions for representing facts, including:</span></span>

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a><span data-ttu-id="bda6b-124">測試 Qubit 狀態</span><span class="sxs-lookup"><span data-stu-id="bda6b-124">Testing Qubit States</span></span> ###

<span data-ttu-id="bda6b-125">實際上，判斷提示會依賴傳統的量子機制模擬不需要遵守[無複製定理](https://arxiv.org/abs/quant-ph/9607018)的事實，因此我們可以在針對目的電腦使用模擬器時，做出 unphysical 測量和判斷提示。</span><span class="sxs-lookup"><span data-stu-id="bda6b-125">In practice, assertions rely on the fact that classical simulations of quantum mechanics need not obey the [no-cloning theorem](https://arxiv.org/abs/quant-ph/9607018), such that we can make unphysical measurements and assertions when using a simulator for our target machine.</span></span>
<span data-ttu-id="bda6b-126">因此，我們可以先在傳統模擬器上測試個別作業，再于硬體上進行部署。</span><span class="sxs-lookup"><span data-stu-id="bda6b-126">Thus, we can test individual operations on a classical simulator before deploying on hardware.</span></span>
<span data-ttu-id="bda6b-127">在不允許評估判斷提示的目的電腦上， <xref:microsoft.quantum.intrinsic.assert> 可以放心忽略的呼叫。</span><span class="sxs-lookup"><span data-stu-id="bda6b-127">On target machines which do not allow evaluation of assertions, calls to <xref:microsoft.quantum.intrinsic.assert> can be safely ignored.</span></span>

<span data-ttu-id="bda6b-128">更常見的情況是，作業判斷提示 <xref:microsoft.quantum.intrinsic.assert> 在給定的 Pauli 基礎測量指定的 qubits 時，一定會有指定的結果。</span><span class="sxs-lookup"><span data-stu-id="bda6b-128">More generally, the <xref:microsoft.quantum.intrinsic.assert> operation asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>
<span data-ttu-id="bda6b-129">如果判斷提示失敗，則會以指定的訊息呼叫來結束執行 `fail` 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-129">If the assertion fails, the execution ends by calling `fail` with the given message.</span></span>
<span data-ttu-id="bda6b-130">根據預設，不會執行這項作業;可支援的模擬器應該提供執行執行時間檢查的執行。</span><span class="sxs-lookup"><span data-stu-id="bda6b-130">By default, this operation is not implemented; simulators that can support it should provide an implementation that performs runtime checking.</span></span>
<span data-ttu-id="bda6b-131">`Assert`具有簽章 `((Pauli[], Qubit[], Result, String) -> ())` 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-131">`Assert` has signature `((Pauli[], Qubit[], Result, String) -> ())`.</span></span>
<span data-ttu-id="bda6b-132">由於 `Assert` 是具有空的元組做為其輸出類型的函式，因此在 `Assert` Q # 程式中不會有任何來自呼叫的效果可觀察。</span><span class="sxs-lookup"><span data-stu-id="bda6b-132">Since `Assert` is a function with an empty tuple as its output type, no effects from having called `Assert` are observable within a Q# program.</span></span>

<span data-ttu-id="bda6b-133">在 <xref:microsoft.quantum.intrinsic.assertprob> 給定的 Pauli 基礎中測量給定 qubits 的運算函式，會在某些容錯範圍內具有給定機率的指定結果。</span><span class="sxs-lookup"><span data-stu-id="bda6b-133">The <xref:microsoft.quantum.intrinsic.assertprob> operation function asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>
<span data-ttu-id="bda6b-134">容錯為加法（例如 `abs(expected-actual) < tol` ）。</span><span class="sxs-lookup"><span data-stu-id="bda6b-134">Tolerance is additive (e.g. `abs(expected-actual) < tol`).</span></span>
<span data-ttu-id="bda6b-135">如果判斷提示失敗，則會以指定的訊息呼叫來結束執行 `fail` 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-135">If the assertion fails, the execution ends by calling `fail` with the given message.</span></span>
<span data-ttu-id="bda6b-136">根據預設，不會執行這項作業;可支援的模擬器應該提供執行執行時間檢查的執行。</span><span class="sxs-lookup"><span data-stu-id="bda6b-136">By default, this operation is not implemented; simulators that can support it should provide an implementation that performs runtime checking.</span></span>
<span data-ttu-id="bda6b-137">`AssertProb`具有簽章 `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-137">`AssertProb` has signature `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`.</span></span> <span data-ttu-id="bda6b-138">第一個 `Double` 參數會提供所需的結果機率，第二個則是容錯。</span><span class="sxs-lookup"><span data-stu-id="bda6b-138">The first of `Double` parameters gives the desired probability of the result, and the second one the tolerance.</span></span>

<span data-ttu-id="bda6b-139">我們可以執行高於單一測量的宣告，使用模擬器用來代表 qubit 內部狀態的傳統資訊適合複製，因此我們不需要實際執行測量來測試判斷提示。</span><span class="sxs-lookup"><span data-stu-id="bda6b-139">We can do more than assert a single measurement, using that the classical information used by a simulator to represent the internal state of a qubit is amenable to copying, such that we do not need to actually perform a measurement to test our assertion.</span></span>
<span data-ttu-id="bda6b-140">特別是，這可讓我們瞭解在實際硬體上可能無法進行的*不相容*測量。</span><span class="sxs-lookup"><span data-stu-id="bda6b-140">In particular, this allows us to reason about *incompatible* measurements that would be impossible on actual hardware.</span></span>

<span data-ttu-id="bda6b-141">假設這 `P : Qubit => Unit` 是一項作業，可在其輸入為 state $ \ket $ 時準備狀態 $ \ket{\psi} $ {0} 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-141">Suppose that `P : Qubit => Unit` is an operation intended to prepare the state $\ket{\psi}$ when its input is in the state $\ket{0}$.</span></span>
<span data-ttu-id="bda6b-142">讓 $ \ket{\psi '} $ 成為所備妥的實際狀態 `P` 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-142">Let $\ket{\psi'}$ be the actual state prepared by `P`.</span></span>
<span data-ttu-id="bda6b-143">然後，只有在 $ \ket{\psi} $ 所描述的軸中測量 $ \ket{\psi '} $ 一律傳回時，$ \ket{\psi} = \ket{\psi '} $ 才會傳回 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-143">Then, $\ket{\psi} = \ket{\psi'}$ if and only if measuring $\ket{\psi'}$ in the axis described by $\ket{\psi}$ always returns `Zero`.</span></span>
<span data-ttu-id="bda6b-144">也就是說，只有在} \braket{\psi | \psi '} = 1 時，\begin{align} \ket{\psi} = \ket{\psi '} 才會 \text{。</span><span class="sxs-lookup"><span data-stu-id="bda6b-144">That is, \begin{align} \ket{\psi} = \ket{\psi'} \text{ if and only if } \braket{\psi | \psi'} = 1.</span></span>
<span data-ttu-id="bda6b-145">\end{align} 使用序言中定義的基本作業，我們可以直接執行測量值，以在 `Zero` $ \ket{\psi} $ 是其中一個 Pauli 運算子的 eigenstate 時傳回。</span><span class="sxs-lookup"><span data-stu-id="bda6b-145">\end{align} Using the primitive operations defined in the prelude, we can directly perform a measurement that returns `Zero` if $\ket{\psi}$ is an eigenstate of one of the Pauli operators.</span></span>


<span data-ttu-id="bda6b-146">當 <xref:microsoft.quantum.diagnostics.assertqubit> 我們想要測試判斷提示 $ \ket{\psi} = \ket $ 時，作業會提供特別有用的縮寫來進行此操作 {0} 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-146">The operation <xref:microsoft.quantum.diagnostics.assertqubit> provides a particularly useful shorthand to do so in the case that we wish to test the assertion $\ket{\psi} = \ket{0}$.</span></span>
<span data-ttu-id="bda6b-147">例如，當我們在釋放 ancilla qubits 至 $ \ket $ 之前，uncomputed 會將 {0} 其傳回。</span><span class="sxs-lookup"><span data-stu-id="bda6b-147">This is common, for instance, when we have uncomputed to return ancilla qubits to $\ket{0}$ before releasing them.</span></span>
<span data-ttu-id="bda6b-148">{0}當我們想要判斷提示兩個狀態準備 `P` 和 `Q` 作業都準備相同的狀態，以及支援時，對 $ \ket $ 進行判斷提示也很有用 `Q` `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-148">Asserting against $\ket{0}$ is also useful when we wish to assert that two state preparation `P` and `Q` operations both prepare the same state, and when `Q` supports `Adjoint`.</span></span>
<span data-ttu-id="bda6b-149">特別是，</span><span class="sxs-lookup"><span data-stu-id="bda6b-149">In particular,</span></span>

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

<span data-ttu-id="bda6b-150">不過，更常見的情況是，我們可能無法存取與 Pauli 運算子 eigenstates 不一致的狀態判斷提示。</span><span class="sxs-lookup"><span data-stu-id="bda6b-150">More generally, however, we may not have access to assertions about states that do not coincide with eigenstates of Pauli operators.</span></span>
<span data-ttu-id="bda6b-151">例如，$ \ket{\psi} = （\ket {0} + e ^ {i \pi/8} \ket {1} ）/\sqrt {2} $ 不是任何 eigenstate 運算子的 Pauli，因此我們無法使用 <xref:microsoft.quantum.intrinsic.assertprob> 來唯一判斷 state $ \ket{\psi '} $ 等於 $ \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="bda6b-151">For example, $\ket{\psi} = (\ket{0} + e^{i \pi / 8} \ket{1}) / \sqrt{2}$ is not an eigenstate of any Pauli operator, such that we cannot use <xref:microsoft.quantum.intrinsic.assertprob> to uniquely determine that a state $\ket{\psi'}$ is equal to $\ket{\psi}$.</span></span>
<span data-ttu-id="bda6b-152">相反地，我們必須將判斷提示 $ \ket{\psi '} = \ket{\psi} $ 分解成可使用模擬器支援的原始物件直接測試的假設。</span><span class="sxs-lookup"><span data-stu-id="bda6b-152">Instead, we must decompose the assertion $\ket{\psi'} = \ket{\psi}$ into assumptions that can be directly tested using  the primitives supported by our simulator.</span></span>
<span data-ttu-id="bda6b-153">若要這麼做，請將 $ \ket{\psi} = \Alpha \ket {0} + \Beta \ket {1} $ 用於複數 $ \Alpha = \_ r + a \_ i $ 和 $ \Beta $。</span><span class="sxs-lookup"><span data-stu-id="bda6b-153">To do so, let $\ket{\psi} = \alpha \ket{0} + \beta \ket{1}$ for complex numbers $\alpha = a\_r + a\_i i$ and $\beta$.</span></span>
<span data-ttu-id="bda6b-154">請注意，此運算式需要四個實數 $ \{ a \_ r、a \_ i、b \_ r、b \_ i \} $ 來指定，因為每個複數都可以表示為實數和虛數部分的總和。</span><span class="sxs-lookup"><span data-stu-id="bda6b-154">Note that this expression requires four real numbers $\{a\_r, a\_i, b\_r, b\_i\}$ to specify, as each complex number can be expressed as the sum of a real and imaginary part.</span></span>
<span data-ttu-id="bda6b-155">不過，由於全域階段，我們可以選擇 $a \_ i = $0，因此我們只需要三個實數來唯一指定單一 qubit 狀態。</span><span class="sxs-lookup"><span data-stu-id="bda6b-155">Due to the global phase, however, we can choose $a\_i = 0$, such that we only need three real numbers to uniquely specify a single-qubit state.</span></span>

<span data-ttu-id="bda6b-156">因此，我們需要指定三個彼此獨立的判斷提示，以便判斷提示所預期的狀態。</span><span class="sxs-lookup"><span data-stu-id="bda6b-156">Thus, we need to specify three assertions which are independent of each other in order to assert the state that we expect.</span></span>
<span data-ttu-id="bda6b-157">我們會藉由找 `Zero` 出每個 Pauli 測量的機率，以提供 $ \Alpha $ 和 $ \Beta $，並個別進行判斷提示。</span><span class="sxs-lookup"><span data-stu-id="bda6b-157">We do so by finding the probability of observing `Zero` for each Pauli measurement given $\alpha$ and $\beta$, and asserting each independently.</span></span>
<span data-ttu-id="bda6b-158">讓 $x $、$y $ 和 $z $ 分別是 `Result` Pauli $X $、$Y $ 和 $Z $ 度量的值。</span><span class="sxs-lookup"><span data-stu-id="bda6b-158">Let $x$, $y$, and $z$ be `Result` values for Pauli $X$, $Y$, and $Z$ measurements respectively.</span></span>
<span data-ttu-id="bda6b-159">然後，使用量測的可能性函式，\begin{align} \Pr （x = \texttt{Zero} | \Alpha，\Beta） & = \frac12 + a \_ r b \_ r + a \_ i b \_ i \\ \\ \Pr （y = \texttt{Zero} | \Alpha，\Beta） & = \frac12 + a \_ r b \_ i-a \_ i b \_ r \\ \\ \Pr （z = \texttt{Zero} | \Alpha，\Beta） & = \frac12\left （1 + a \_ r ^ 2 + a \_ i ^ 2 + b \_ r ^ 2 + b \_ i ^ 2 \right）。</span><span class="sxs-lookup"><span data-stu-id="bda6b-159">Then, using the likelihood function for quantum measurements, \begin{align} \Pr(x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ \Pr(y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_i - a\_i b\_r \\\\ \Pr(z = \texttt{Zero} | \alpha, \beta) & = \frac12\left( 1 + a\_r^2 + a\_i^2 + b\_r^2 + b\_i^2 \right).</span></span>
<span data-ttu-id="bda6b-160">\end{align}</span><span class="sxs-lookup"><span data-stu-id="bda6b-160">\end{align}</span></span>

<span data-ttu-id="bda6b-161">作業會 <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 以類型的值，將指定的 $ \Alpha $ 和 $ \Beta $ 標記法實作為這些判斷提示 <xref:microsoft.quantum.math.complex> 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-161">The <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> operation implements these assertions given representations of $\alpha$ and $\beta$ as values of type <xref:microsoft.quantum.math.complex>.</span></span>
<span data-ttu-id="bda6b-162">當預期的狀態可以數學計算時，這會很有説明。</span><span class="sxs-lookup"><span data-stu-id="bda6b-162">This is helpful when the expected state can be computed mathematically.</span></span>

### <a name="asserting-equality-of-quantum-operations"></a><span data-ttu-id="bda6b-163">判斷量子作業是否相等</span><span class="sxs-lookup"><span data-stu-id="bda6b-163">Asserting Equality of Quantum Operations</span></span> ###

<span data-ttu-id="bda6b-164">到目前為止，我們都擔心要準備特定狀態的測試作業。</span><span class="sxs-lookup"><span data-stu-id="bda6b-164">Thus far, we have been concerned with testing operations which are intended to prepare particular states.</span></span>
<span data-ttu-id="bda6b-165">不過，通常我們會對任意輸入（而不是單一固定輸入）的操作方式感興趣。</span><span class="sxs-lookup"><span data-stu-id="bda6b-165">Often, however, we are interested in how an operation acts for arbitrary inputs rather than for a single fixed input.</span></span>
<span data-ttu-id="bda6b-166">例如，假設我們已實作為 `U : ((Double, Qubit[]) => () : Adjoint)` 一個對應于一系列單一運算子 $U （t） $ 的作業，並提供明確的 `adjoint` 區塊，而不是使用 `adjoint auto` 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-166">For example, suppose we have implemented an operation `U : ((Double, Qubit[]) => () : Adjoint)` corresponding to a family of unitary operators $U(t)$, and have provided an explicit `adjoint` block instead of using `adjoint auto`.</span></span>
<span data-ttu-id="bda6b-167">如果 $t $ 代表進化時間，我們可能會想要判斷提示 $U ^ \dagger （t） = U （-t） $ （如預期）。</span><span class="sxs-lookup"><span data-stu-id="bda6b-167">We may be interested in asserting that $U^\dagger(t) = U(-t)$, as expected if $t$ represents an evolution time.</span></span>

<span data-ttu-id="bda6b-168">大致來說，我們可以遵循兩個不同的策略，讓判斷提示中的兩個作業 `U` 和 `V` 動作都相同。</span><span class="sxs-lookup"><span data-stu-id="bda6b-168">Broadly speaking, there are two different strategies that we can follow in making the assertion that two operations `U` and `V` act identically.</span></span>
<span data-ttu-id="bda6b-169">首先，我們可以檢查 `U(target); (Adjoint V)(target);` 以指定的方式來保留每個狀態。</span><span class="sxs-lookup"><span data-stu-id="bda6b-169">First, we can check that `U(target); (Adjoint V)(target);` preserves each state in a given basis.</span></span>
<span data-ttu-id="bda6b-170">第二，我們可以檢查，以 `U(target); (Adjoint V)(target);` 光子狀態的一半來保留該會任何牽連。</span><span class="sxs-lookup"><span data-stu-id="bda6b-170">Second, we can check that `U(target); (Adjoint V)(target);` acting on half of an entangled state preserves that entanglement.</span></span>
<span data-ttu-id="bda6b-171">這些策略是由 canon 作業 <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> 和分別執行 <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced> 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-171">These strategies are implemented by the canon operations <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> and <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="bda6b-172">上述所討論的參考判斷提示適用于[Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)，這是一種數學架構，其會將 $n $ qubits 上的作業與 $ 2n $ 光子上的 qubits 狀態相關聯。</span><span class="sxs-lookup"><span data-stu-id="bda6b-172">The referenced assertion discussed above works based on the [Choi–Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), a mathematical framework which relates operations on $n$ qubits to entangled states on $2n$ qubits.</span></span>
> <span data-ttu-id="bda6b-173">特別是，$n $ qubits 上的身分識別作業是由光子 state $ \ket{\ Beta_ {00} } \mathrel{： =} （\ket {00} + \ket {11} ）/\sqrt $ 的 $n $ 複本所表示 {2} 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-173">In particular, the identity operation on $n$ qubits is represented by $n$ copies of the entangled state $\ket{\beta_{00}} \mathrel{:=} (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span>
> <span data-ttu-id="bda6b-174">作業 <xref:microsoft.quantum.preparation.preparechoistate> 會執行此 isomorphism，並準備代表給定作業的狀態。</span><span class="sxs-lookup"><span data-stu-id="bda6b-174">The operation <xref:microsoft.quantum.preparation.preparechoistate> implements this isomorphism, preparing a state that represents a given operation.</span></span>

<span data-ttu-id="bda6b-175">大致上，這些策略會以時間-空間取捨來區分。</span><span class="sxs-lookup"><span data-stu-id="bda6b-175">Roughly, these strategies are distinguished by a time–space tradeoff.</span></span>
<span data-ttu-id="bda6b-176">逐一查看每個輸入狀態需要額外的時間，而使用會任何牽連做為參考時，需要儲存額外的 qubits。</span><span class="sxs-lookup"><span data-stu-id="bda6b-176">Iterating through each input state takes additional time, while using entanglement as a reference requires storing additional qubits.</span></span>
<span data-ttu-id="bda6b-177">在作業執行可復原的傳統作業的情況下，我們只會對其運算基礎狀態的行為感興趣， <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> 測試此限制的輸入集合是否相等。</span><span class="sxs-lookup"><span data-stu-id="bda6b-177">In cases where an operation implements a reversible classical operation, such that we are only interested in its behavior on computational basis states, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> tests equality on this restricted set of inputs.</span></span>

> [!TIP]
> <span data-ttu-id="bda6b-178">輸入狀態的反復專案是由列舉作業和處理 <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> <xref:microsoft.quantum.canon.iteratethroughcartesianpower> 。</span><span class="sxs-lookup"><span data-stu-id="bda6b-178">The iteration over input states is handled by the enumeration operations <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> and <xref:microsoft.quantum.canon.iteratethroughcartesianpower>.</span></span>
> <span data-ttu-id="bda6b-179">在兩個或多個集合之間將作業套用至笛卡兒產品的每個元素時，這些作業會更有用。</span><span class="sxs-lookup"><span data-stu-id="bda6b-179">These operations are useful more generally for applying an operation to each element of the Cartesian product between two or more sets.</span></span>

<span data-ttu-id="bda6b-180">不過，這兩種方法會對受測作業的不同屬性進行測試。</span><span class="sxs-lookup"><span data-stu-id="bda6b-180">More critically, however, the two approaches test different properties of the operations under examination.</span></span>
<span data-ttu-id="bda6b-181">由於就地判斷提示會多次呼叫每個作業，因此針對每個輸入狀態，任何隨機的選擇和測量結果可能會在呼叫之間變更。</span><span class="sxs-lookup"><span data-stu-id="bda6b-181">Since the in-place assertion calls each operation multiple times, once for each input state, any random choices and measurement results might change between calls.</span></span>
<span data-ttu-id="bda6b-182">相較之下，參考的判斷提示只會呼叫每個作業一次，因此它會檢查*單一快照中*的作業是否相等。</span><span class="sxs-lookup"><span data-stu-id="bda6b-182">By contrast, the referenced assertion calls each operation exactly once, such that it checks that the operations are equal *in a single shot*.</span></span>
<span data-ttu-id="bda6b-183">這兩個測試都有助於確保量副程式的正確性。</span><span class="sxs-lookup"><span data-stu-id="bda6b-183">Both of these tests are useful in ensuring the correctness of quantum programs.</span></span>


## <a name="further-reading"></a><span data-ttu-id="bda6b-184">深入閱讀</span><span class="sxs-lookup"><span data-stu-id="bda6b-184">Further Reading</span></span> ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:microsoft.quantum.diagnostics>
