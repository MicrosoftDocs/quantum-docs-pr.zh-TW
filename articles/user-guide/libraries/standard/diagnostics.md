---
title: 標準程式庫中的診斷 Q#
description: 瞭解在 Q# 量副程式中用來攔截錯誤或錯誤的標準程式庫中的診斷功能和作業。
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: d13122187a24893d297cfdbb3ad4db03eb22ded0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858689"
---
# <a name="diagnostics"></a><span data-ttu-id="46fff-103">診斷</span><span class="sxs-lookup"><span data-stu-id="46fff-103">Diagnostics</span></span> #

<span data-ttu-id="46fff-104">就像傳統開發一樣，要能夠診斷量副程式中的錯誤和錯誤是很重要的。</span><span class="sxs-lookup"><span data-stu-id="46fff-104">As with classical development, it is important to be able to diagnose mistakes and errors in quantum programs.</span></span>
<span data-ttu-id="46fff-105">Q#標準程式庫提供各種不同的方式來確保量副程式的正確性，如中所述 <xref:microsoft.quantum.guide.testingdebugging> 。</span><span class="sxs-lookup"><span data-stu-id="46fff-105">The Q# standard libraries provide a variety of different ways to ensure the correctness of quantum programs, as detailed in <xref:microsoft.quantum.guide.testingdebugging>.</span></span>
<span data-ttu-id="46fff-106">大致上來說，這項支援的形式為函式和作業，可指示目的電腦為主機程式或開發人員提供額外的診斷資訊，或強制執行函式或作業呼叫所表示的條件和非變異的正確性。</span><span class="sxs-lookup"><span data-stu-id="46fff-106">Largely speaking, this support comes in the form of functions and operations that either instruct the target machine to provide additional diagnostic information to the host program or developer, or enforce the correctness of conditions and invariants expressed by the function or operation call.</span></span>

## <a name="machine-diagnostics"></a><span data-ttu-id="46fff-107">機器診斷</span><span class="sxs-lookup"><span data-stu-id="46fff-107">Machine Diagnostics</span></span> ##

<span data-ttu-id="46fff-108">您可以使用函 <xref:Microsoft.Quantum.Intrinsic.Message> 式以電腦相依的方式來記錄訊息，以取得有關傳統值的診斷功能。</span><span class="sxs-lookup"><span data-stu-id="46fff-108">Diagnostics about classical values can be obtained by using the <xref:Microsoft.Quantum.Intrinsic.Message> function to log a message in a machine-dependent way.</span></span>
<span data-ttu-id="46fff-109">根據預設，這會將字串寫入主控台。</span><span class="sxs-lookup"><span data-stu-id="46fff-109">By default, this writes the string to the console.</span></span>
<span data-ttu-id="46fff-110">與內插字串一起使用， <xref:Microsoft.Quantum.Intrinsic.Message> 可讓您輕鬆地報告有關傳統值的診斷資訊：</span><span class="sxs-lookup"><span data-stu-id="46fff-110">Used together with interpolated strings, <xref:Microsoft.Quantum.Intrinsic.Message> makes it easy to report diagnostic information about classical values:</span></span>

```qsharp
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> <span data-ttu-id="46fff-111">`Message` 有簽章 `(String -> Unit)` ，但無法從內觀察發出的偵錯工具記錄訊息 Q# 。</span><span class="sxs-lookup"><span data-stu-id="46fff-111">`Message` has signature `(String -> Unit)`, again representing that emitting a debug log message cannot be observed from within Q#.</span></span>

<span data-ttu-id="46fff-112"><xref:Microsoft.Quantum.Diagnostics.DumpMachine>和 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> callables 指示目的電腦，以提供有關目前已配置之量子位的診斷資訊，或分別提供量子位的特定註冊。</span><span class="sxs-lookup"><span data-stu-id="46fff-112">The <xref:Microsoft.Quantum.Diagnostics.DumpMachine> and <xref:Microsoft.Quantum.Diagnostics.DumpRegister> callables instruct target machines to provide diagnostic information about all currently allocated qubits or about a specific register of qubits, respectively.</span></span>
<span data-ttu-id="46fff-113">每一部目的電腦都有不同的診斷資訊，以回應傾印指令。</span><span class="sxs-lookup"><span data-stu-id="46fff-113">Each target machine varies in what diagnostic information is provided in response to a dump instruction.</span></span>
<span data-ttu-id="46fff-114">例如， [完整狀態](xref:microsoft.quantum.machines.full-state-simulator) 模擬器目的電腦提供的主機程式具有在內部用來代表量子位註冊的狀態向量。</span><span class="sxs-lookup"><span data-stu-id="46fff-114">The [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) target machine, for instance, provides the host program with the state vector that it uses internally to represent a register of qubits.</span></span>
<span data-ttu-id="46fff-115">相較之下， [Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) 模擬器目的電腦為每個量子位提供單一的傳統位。</span><span class="sxs-lookup"><span data-stu-id="46fff-115">By comparison, the [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator) target machine provides a single classical bit for each qubit.</span></span>

 <span data-ttu-id="46fff-116">若要深入瞭解 [完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器的 `DumpMachine` 輸出，請參閱 [測試和偵錯工具文章](xref:microsoft.quantum.guide.testingdebugging#dump-functions)的傾印函式一節。</span><span class="sxs-lookup"><span data-stu-id="46fff-116">To learn more about the [full state simulator's](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` output, take a look at the dump functions section of our [testing and debugging article](xref:microsoft.quantum.guide.testingdebugging#dump-functions).</span></span>


## <a name="facts-and-assertions"></a><span data-ttu-id="46fff-117">事實和判斷提示</span><span class="sxs-lookup"><span data-stu-id="46fff-117">Facts and Assertions</span></span> ##

<span data-ttu-id="46fff-118">如 [測試和](xref:microsoft.quantum.guide.testingdebugging)偵測所述，可以將具有簽章或的函式或作業 `Unit -> Unit` `Unit => Unit` 分別標示為 *單元測試*。</span><span class="sxs-lookup"><span data-stu-id="46fff-118">As discussed in [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging), a function or operation with signature `Unit -> Unit` or `Unit => Unit`, respectively, can be marked as a *unit test*.</span></span>
<span data-ttu-id="46fff-119">每個單元測試通常包含一個小的量副程式，以及一個或多個檢查該程式是否正確的條件。</span><span class="sxs-lookup"><span data-stu-id="46fff-119">Each unit test generally consists of a small quantum program, along with one or more conditions that check the correctness of that program.</span></span>
<span data-ttu-id="46fff-120">這些條件可以是任一 _事實_ 的形式，它會檢查輸入的值或 _判斷_ 提示的值，以檢查傳遞給輸入的一或多個量子位的狀態。</span><span class="sxs-lookup"><span data-stu-id="46fff-120">These conditions can come in the form of either _facts_, which check the values of their inputs, or _assertions_, which check the states of one or more qubits passed as input.</span></span>

<span data-ttu-id="46fff-121">例如， `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` 代表 $1 + 1 = $2 的數學事實，而 `AssertQubit(One, qubit)` 表示測量會傳回確定性的條件 `qubit` `One` 。</span><span class="sxs-lookup"><span data-stu-id="46fff-121">For example, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` represents the mathematical fact that $1 + 1 = 2$, while `AssertQubit(One, qubit)` represents the condition that measuring `qubit` will return a `One` with certainty.</span></span>
<span data-ttu-id="46fff-122">在先前的案例中，我們只會檢查指定值的正確性，但在後者中，我們必須知道量子位狀態的相關資訊，才能評估判斷提示。</span><span class="sxs-lookup"><span data-stu-id="46fff-122">In the former case, we can check the correctness of the condition given only its values, while in the latter, we must know something about the state of the qubit in order to evaluate the assertion.</span></span>

<span data-ttu-id="46fff-123">Q#標準程式庫提供數個代表事實的不同函式，包括：</span><span class="sxs-lookup"><span data-stu-id="46fff-123">The Q# standard libraries provide several different functions for representing facts, including:</span></span>

- <xref:Microsoft.Quantum.Diagnostics.Fact>
- <xref:Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact>
- <xref:Microsoft.Quantum.Diagnostics.NearEqualityFactC>
- <xref:Microsoft.Quantum.Diagnostics.EqualityFactI>


### <a name="testing-qubit-states"></a><span data-ttu-id="46fff-124">測試量子位狀態</span><span class="sxs-lookup"><span data-stu-id="46fff-124">Testing Qubit States</span></span> ###

<span data-ttu-id="46fff-125">在實務上，判斷提示會依賴量子機制的傳統模擬不需要遵守 [無複製定理](https://arxiv.org/abs/quant-ph/9607018)，因此我們可以在為目的電腦使用模擬器時，進行 unphysical 測量和判斷提示。</span><span class="sxs-lookup"><span data-stu-id="46fff-125">In practice, assertions rely on the fact that classical simulations of quantum mechanics need not obey the [no-cloning theorem](https://arxiv.org/abs/quant-ph/9607018), such that we can make unphysical measurements and assertions when using a simulator for our target machine.</span></span>
<span data-ttu-id="46fff-126">因此，我們可以在傳統模擬器上測試個別的作業，然後再于硬體上進行部署。</span><span class="sxs-lookup"><span data-stu-id="46fff-126">Thus, we can test individual operations on a classical simulator before deploying on hardware.</span></span>
<span data-ttu-id="46fff-127">在不允許評估判斷提示的目的電腦上， <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> 可以安全地忽略的呼叫。</span><span class="sxs-lookup"><span data-stu-id="46fff-127">On target machines which do not allow evaluation of assertions, calls to <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> can be safely ignored.</span></span>

<span data-ttu-id="46fff-128">更常見的情況是，作業會判斷提示 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> 以指定的 Pauli 為基礎來測量指定的量子位，一律會有指定的結果。</span><span class="sxs-lookup"><span data-stu-id="46fff-128">More generally, the <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> operation asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>
<span data-ttu-id="46fff-129">如果判斷提示失敗，則會以指定的訊息呼叫來結束執行 `fail` 。</span><span class="sxs-lookup"><span data-stu-id="46fff-129">If the assertion fails, the run ends by calling `fail` with the given message.</span></span>
<span data-ttu-id="46fff-130">依預設，不會執行這項作業;可以支援的模擬器應該提供執行執行時間檢查的執行。</span><span class="sxs-lookup"><span data-stu-id="46fff-130">By default, this operation is not implemented; simulators that can support it should provide an implementation that performs runtime checking.</span></span>
<span data-ttu-id="46fff-131">`AssertMeasurement` 有簽章 `((Pauli[], Qubit[], Result, String) -> ())` 。</span><span class="sxs-lookup"><span data-stu-id="46fff-131">`AssertMeasurement` has signature `((Pauli[], Qubit[], Result, String) -> ())`.</span></span>
<span data-ttu-id="46fff-132">因為 `AssertMeasurement` 是具有空的元組作為其輸出類型的函式，所以在 `AssertMeasurement` 程式內不會有呼叫的影響 Q# 。</span><span class="sxs-lookup"><span data-stu-id="46fff-132">Since `AssertMeasurement` is a function with an empty tuple as its output type, no effects from having called `AssertMeasurement` are observable within a Q# program.</span></span>

<span data-ttu-id="46fff-133">作業函式會判斷提示 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> ，以指定的 Pauli 為基礎來測量指定的量子位，在部分容錯範圍內會有給定機率的指定結果。</span><span class="sxs-lookup"><span data-stu-id="46fff-133">The <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> operation function asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>
<span data-ttu-id="46fff-134">容錯是加法 (例如 `abs(expected-actual) < tol`) 。</span><span class="sxs-lookup"><span data-stu-id="46fff-134">Tolerance is additive (for example, `abs(expected-actual) < tol`).</span></span>
<span data-ttu-id="46fff-135">如果判斷提示失敗，則會以指定的訊息呼叫來結束執行 `fail` 。</span><span class="sxs-lookup"><span data-stu-id="46fff-135">If the assertion fails, the run ends by calling `fail` with the given message.</span></span>
<span data-ttu-id="46fff-136">依預設，不會執行這項作業;可以支援的模擬器應該提供執行執行時間檢查的執行。</span><span class="sxs-lookup"><span data-stu-id="46fff-136">By default, this operation is not implemented; simulators that can support it should provide an implementation that performs runtime checking.</span></span>
<span data-ttu-id="46fff-137">`AssertMeasurementProbability` 有簽章 `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="46fff-137">`AssertMeasurementProbability` has signature `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`.</span></span> <span data-ttu-id="46fff-138">第一個 `Double` 參數會提供所需的結果機率，而第二個則是容錯。</span><span class="sxs-lookup"><span data-stu-id="46fff-138">The first of `Double` parameters gives the desired probability of the result, and the second one the tolerance.</span></span>

<span data-ttu-id="46fff-139">我們可以使用模擬器所用的傳統資訊來代表量子位的內部狀態，以進行複製，而不需要實際執行測量以測試我們的判斷提示，就可以進行一次以上的測量。</span><span class="sxs-lookup"><span data-stu-id="46fff-139">We can do more than assert a single measurement, using that the classical information used by a simulator to represent the internal state of a qubit is amenable to copying, such that we do not need to actually perform a measurement to test our assertion.</span></span>
<span data-ttu-id="46fff-140">尤其是，這可讓我們瞭解在實際硬體上可能不可能發生 *不相容* 的度量的原因。</span><span class="sxs-lookup"><span data-stu-id="46fff-140">In particular, this allows us to reason about *incompatible* measurements that would be impossible on actual hardware.</span></span>

<span data-ttu-id="46fff-141">假設這 `P : Qubit => Unit` 是一項作業，目的是要在它的輸入處於狀態 $ \ket $ 時準備狀態 $ \ket{\psi} $ {0} 。</span><span class="sxs-lookup"><span data-stu-id="46fff-141">Suppose that `P : Qubit => Unit` is an operation intended to prepare the state $\ket{\psi}$ when its input is in the state $\ket{0}$.</span></span>
<span data-ttu-id="46fff-142">Let $ \ket{\psi '} $ 是所準備的實際狀態 `P` 。</span><span class="sxs-lookup"><span data-stu-id="46fff-142">Let $\ket{\psi'}$ be the actual state prepared by `P`.</span></span>
<span data-ttu-id="46fff-143">然後，只有在 $ \ket{\psi} $ 所描述的座標軸中測量 $ \ket{\psi '} $ 時，才會傳回 $ \ket{\psi} = \ket{\psi '} $ `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="46fff-143">Then, $\ket{\psi} = \ket{\psi'}$ if and only if measuring $\ket{\psi'}$ in the axis described by $\ket{\psi}$ always returns `Zero`.</span></span>
<span data-ttu-id="46fff-144">也就是說，\begin{align} \ket{\psi} = \ket{\psi '} \text{if and only} \braket{\psi | \psi '} = 1。</span><span class="sxs-lookup"><span data-stu-id="46fff-144">That is, \begin{align} \ket{\psi} = \ket{\psi'} \text{ if and only if } \braket{\psi | \psi'} = 1.</span></span>
<span data-ttu-id="46fff-145">\end{align} 使用在序言中定義的基本作業，我們可以直接執行測量，以傳回 `Zero` $ \ket{\psi} $ 是否為其中一個 Pauli 運算子的 eigenstate。</span><span class="sxs-lookup"><span data-stu-id="46fff-145">\end{align} Using the primitive operations defined in the prelude, we can directly perform a measurement that returns `Zero` if $\ket{\psi}$ is an eigenstate of one of the Pauli operators.</span></span>


<span data-ttu-id="46fff-146">當 <xref:Microsoft.Quantum.Diagnostics.AssertQubit> 我們想要測試判斷提示 $ \ket{\psi} = \ket $ 時，此作業會提供特別實用的速記來進行這項操作 {0} 。</span><span class="sxs-lookup"><span data-stu-id="46fff-146">The operation <xref:Microsoft.Quantum.Diagnostics.AssertQubit> provides a particularly useful shorthand to do so in the case that we wish to test the assertion $\ket{\psi} = \ket{0}$.</span></span>
<span data-ttu-id="46fff-147">這種情況很常見，例如，當我們在釋放 ancilla 量子位至 $ \ket $ 之前，我們有 uncomputed {0} 。</span><span class="sxs-lookup"><span data-stu-id="46fff-147">This is common, for instance, when we have uncomputed to return ancilla qubits to $\ket{0}$ before releasing them.</span></span>
<span data-ttu-id="46fff-148">{0}當我們想要判斷提示兩個狀態準備 `P` 和 `Q` 作業都準備相同的狀態，而且支援時，對 $ \ket $ 的判斷提示也很有用 `Q` `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="46fff-148">Asserting against $\ket{0}$ is also useful when we wish to assert that two state preparation `P` and `Q` operations both prepare the same state, and when `Q` supports `Adjoint`.</span></span>
<span data-ttu-id="46fff-149">尤其是</span><span class="sxs-lookup"><span data-stu-id="46fff-149">In particular,</span></span>

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

<span data-ttu-id="46fff-150">不過，更常見的情況是，我們可能無法存取與 Pauli 運算子 eigenstates 不一致的狀態判斷提示。</span><span class="sxs-lookup"><span data-stu-id="46fff-150">More generally, however, we may not have access to assertions about states that do not coincide with eigenstates of Pauli operators.</span></span>
<span data-ttu-id="46fff-151">例如，$ \ket{\psi} = ( \ket {0} + e ^ {i \pi/8} \ket {1}) /\sqrt {2} $ 不是任何 eigenstate 運算子的 Pauli，因此我們無法用 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 來唯一判斷 state $ \ket{\psi '} $ 等於 $ \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="46fff-151">For example, $\ket{\psi} = (\ket{0} + e^{i \pi / 8} \ket{1}) / \sqrt{2}$ is not an eigenstate of any Pauli operator, such that we cannot use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> to uniquely determine that a state $\ket{\psi'}$ is equal to $\ket{\psi}$.</span></span>
<span data-ttu-id="46fff-152">相反地，我們必須將判斷提示 $ \ket{\psi '} = \ket{\psi} $ 分解成可使用模擬器所支援的基本專案直接測試的假設。</span><span class="sxs-lookup"><span data-stu-id="46fff-152">Instead, we must decompose the assertion $\ket{\psi'} = \ket{\psi}$ into assumptions that can be directly tested using  the primitives supported by our simulator.</span></span>
<span data-ttu-id="46fff-153">若要這樣做，請將 $ \ket{\psi} = \Alpha \ket {0} + \Beta \ket {1} $ 用於複數 $ \Alpha = a \_ i r + a \_ i $ 和 $ \Beta $。</span><span class="sxs-lookup"><span data-stu-id="46fff-153">To do so, let $\ket{\psi} = \alpha \ket{0} + \beta \ket{1}$ for complex numbers $\alpha = a\_r + a\_i i$ and $\beta$.</span></span>
<span data-ttu-id="46fff-154">請注意，這個運算式需要四個實數 $ \{ a \_ r、 \_ i、b \_ r、b \_ i \} $ 來指定，因為每一個複數都可以表示成實數和虛數部分的總和。</span><span class="sxs-lookup"><span data-stu-id="46fff-154">Note that this expression requires four real numbers $\{a\_r, a\_i, b\_r, b\_i\}$ to specify, as each complex number can be expressed as the sum of a real and imaginary part.</span></span>
<span data-ttu-id="46fff-155">不過，由於全球階段的緣故，我們可以選擇 $a \_ i = $0，因此我們只需要三個實數才能唯一指定單一量子位的狀態。</span><span class="sxs-lookup"><span data-stu-id="46fff-155">Due to the global phase, however, we can choose $a\_i = 0$, such that we only need three real numbers to uniquely specify a single-qubit state.</span></span>

<span data-ttu-id="46fff-156">因此，我們需要指定三個彼此獨立的判斷提示，以判斷提示所預期的狀態。</span><span class="sxs-lookup"><span data-stu-id="46fff-156">Thus, we need to specify three assertions which are independent of each other in order to assert the state that we expect.</span></span>
<span data-ttu-id="46fff-157">我們的做法是找 `Zero` 出每個 Pauli 測量值的觀察到 $ \Alpha $ 和 $ \Beta $，然後個別判斷提示。</span><span class="sxs-lookup"><span data-stu-id="46fff-157">We do so by finding the probability of observing `Zero` for each Pauli measurement given $\alpha$ and $\beta$, and asserting each independently.</span></span>
<span data-ttu-id="46fff-158">讓 $x $、$y $ 和 $z $ 分別為 `Result` Pauli $X $、$Y $ 和 $Z $ 度量的值。</span><span class="sxs-lookup"><span data-stu-id="46fff-158">Let $x$, $y$, and $z$ be `Result` values for Pauli $X$, $Y$, and $Z$ measurements respectively.</span></span>
<span data-ttu-id="46fff-159">然後，使用量子測量的可能性函數，\begin{align} \Pr (x = \texttt{Zero} |\Alpha、\Beta) & = \frac12 + a \_ r b \_ r + a \_ i b \_ i \\ \\ \Pr (y = \texttt{Zero} | \Alpha，\Beta) & = \frac12 + a \_ r b \_ i-a \_ i b \_ r \\ \\ \Pr (z = \texttt{Zero} | \Alpha，\Beta) & = \frac12\left ( 1 + a \_ r ^ 2 + a \_ i ^ 2 + b r ^ 2 + \_ b \_ i ^ 2 \right) 。</span><span class="sxs-lookup"><span data-stu-id="46fff-159">Then, using the likelihood function for quantum measurements, \begin{align} \Pr(x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ \Pr(y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_i - a\_i b\_r \\\\ \Pr(z = \texttt{Zero} | \alpha, \beta) & = \frac12\left( 1 + a\_r^2 + a\_i^2 + b\_r^2 + b\_i^2 \right).</span></span>
<span data-ttu-id="46fff-160">\end{align}</span><span class="sxs-lookup"><span data-stu-id="46fff-160">\end{align}</span></span>

<span data-ttu-id="46fff-161">作業會在 <xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance> 指定的 $ \Alpha $ 和 $ \Beta $ 標記法中，將這些判斷提示實作為型別的值 <xref:Microsoft.Quantum.Math.Complex> 。</span><span class="sxs-lookup"><span data-stu-id="46fff-161">The <xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance> operation implements these assertions given representations of $\alpha$ and $\beta$ as values of type <xref:Microsoft.Quantum.Math.Complex>.</span></span>
<span data-ttu-id="46fff-162">當預期的狀態可以數學計算時，這會很有説明。</span><span class="sxs-lookup"><span data-stu-id="46fff-162">This is helpful when the expected state can be computed mathematically.</span></span>

### <a name="asserting-equality-of-quantum-operations"></a><span data-ttu-id="46fff-163">判斷提示與量子作業是否相等</span><span class="sxs-lookup"><span data-stu-id="46fff-163">Asserting Equality of Quantum Operations</span></span> ###

<span data-ttu-id="46fff-164">到目前為止，我們都擔心要準備特定狀態的測試作業。</span><span class="sxs-lookup"><span data-stu-id="46fff-164">Thus far, we have been concerned with testing operations which are intended to prepare particular states.</span></span>
<span data-ttu-id="46fff-165">但通常，我們會對任意輸入（而不是單一固定輸入）的運作方式有興趣。</span><span class="sxs-lookup"><span data-stu-id="46fff-165">Often, however, we are interested in how an operation acts for arbitrary inputs rather than for a single fixed input.</span></span>
<span data-ttu-id="46fff-166">例如，假設我們已將 `U : ((Double, Qubit[]) => () : Adjoint)` 對應至單一單一運算子系列的作業，$U (t) $，並提供明確 `adjoint` 的區塊，而不是使用 `adjoint auto` 。</span><span class="sxs-lookup"><span data-stu-id="46fff-166">For example, suppose we have implemented an operation `U : ((Double, Qubit[]) => () : Adjoint)` corresponding to a family of unitary operators $U(t)$, and have provided an explicit `adjoint` block instead of using `adjoint auto`.</span></span>
<span data-ttu-id="46fff-167">我們可能會想要判斷提示 $U ^ \dagger (t) = U (-t) $，如 $t $ 代表演進時間所預期。</span><span class="sxs-lookup"><span data-stu-id="46fff-167">We may be interested in asserting that $U^\dagger(t) = U(-t)$, as expected if $t$ represents an evolution time.</span></span>

<span data-ttu-id="46fff-168">大致上說，有兩個不同的策略可讓判斷提示指出這兩個作業 `U` ，並以相同的方式執行 `V` 。</span><span class="sxs-lookup"><span data-stu-id="46fff-168">Broadly speaking, there are two different strategies that we can follow in making the assertion that two operations `U` and `V` act identically.</span></span>
<span data-ttu-id="46fff-169">首先，我們可以檢查 `U(target); (Adjoint V)(target);` 以指定的為基礎來保留每個狀態。</span><span class="sxs-lookup"><span data-stu-id="46fff-169">First, we can check that `U(target); (Adjoint V)(target);` preserves each state in a given basis.</span></span>
<span data-ttu-id="46fff-170">其次，我們可以檢查是否 `U(target); (Adjoint V)(target);` 有一半的纏結狀態會保留該纏結。</span><span class="sxs-lookup"><span data-stu-id="46fff-170">Second, we can check that `U(target); (Adjoint V)(target);` acting on half of an entangled state preserves that entanglement.</span></span>
<span data-ttu-id="46fff-171">這些策略是由 canon 作業 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> 和分別執行 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> 。</span><span class="sxs-lookup"><span data-stu-id="46fff-171">These strategies are implemented by the canon operations <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> and <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced>, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="46fff-172">以上所討論的參考判斷提示會以 [choi 對於– Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)為基礎，這是一種數學架構，會將 $n $ 量子位上的作業與 $ 2n $ 纏結上的量子位狀態相關聯。</span><span class="sxs-lookup"><span data-stu-id="46fff-172">The referenced assertion discussed above works based on the [Choi–Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), a mathematical framework which relates operations on $n$ qubits to entangled states on $2n$ qubits.</span></span>
> <span data-ttu-id="46fff-173">尤其是，$n $ 量子位上的身分識別作業會以纏結 state $ \ket{\ Beta_ {00} } \mathrel{： =} ( \ket {00} + \ket {11}) /\sqrt $ 的 $n $ 副本表示 {2} 。</span><span class="sxs-lookup"><span data-stu-id="46fff-173">In particular, the identity operation on $n$ qubits is represented by $n$ copies of the entangled state $\ket{\beta_{00}} \mathrel{:=} (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span>
> <span data-ttu-id="46fff-174">作業 <xref:Microsoft.Quantum.Preparation.PrepareChoiState> 會執行這個 isomorphism，準備代表指定作業的狀態。</span><span class="sxs-lookup"><span data-stu-id="46fff-174">The operation <xref:Microsoft.Quantum.Preparation.PrepareChoiState> implements this isomorphism, preparing a state that represents a given operation.</span></span>

<span data-ttu-id="46fff-175">大致上，這些策略會以時間（空間折衷）來區分。</span><span class="sxs-lookup"><span data-stu-id="46fff-175">Roughly, these strategies are distinguished by a time–space tradeoff.</span></span>
<span data-ttu-id="46fff-176">逐一查看每個輸入狀態需要額外的時間，而使用纏結作為參考需要儲存額外的量子位。</span><span class="sxs-lookup"><span data-stu-id="46fff-176">Iterating through each input state takes additional time, while using entanglement as a reference requires storing additional qubits.</span></span>
<span data-ttu-id="46fff-177">如果作業會執行可還原的傳統作業，讓我們只對計算基礎狀態的行為感興趣，則 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis> 測試這組有限的輸入是否相等。</span><span class="sxs-lookup"><span data-stu-id="46fff-177">In cases where an operation implements a reversible classical operation, such that we are only interested in its behavior on computational basis states, <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis> tests equality on this restricted set of inputs.</span></span>

> [!TIP]
> <span data-ttu-id="46fff-178">輸入狀態的反復專案是由列舉作業和所 <xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct> 處理 <xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower> 。</span><span class="sxs-lookup"><span data-stu-id="46fff-178">The iteration over input states is handled by the enumeration operations <xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct> and <xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower>.</span></span>
> <span data-ttu-id="46fff-179">這些作業對於將作業套用到兩個或多個集合之間的笛卡兒乘積的每個元素，更是很有用。</span><span class="sxs-lookup"><span data-stu-id="46fff-179">These operations are useful more generally for applying an operation to each element of the Cartesian product between two or more sets.</span></span>

<span data-ttu-id="46fff-180">不過，這兩種方法會測試所檢查之作業的不同屬性。</span><span class="sxs-lookup"><span data-stu-id="46fff-180">More critically, however, the two approaches test different properties of the operations under examination.</span></span>
<span data-ttu-id="46fff-181">因為就地判斷提示會多次呼叫每個作業，每個輸入狀態一次，任何隨機播放和測量結果可能會在呼叫之間變更。</span><span class="sxs-lookup"><span data-stu-id="46fff-181">Since the in-place assertion calls each operation multiple times, once for each input state, any random choices and measurement results might change between calls.</span></span>
<span data-ttu-id="46fff-182">相反地，參考的判斷提示會一次呼叫每個作業一次，因此它會檢查作業是否等於 *單一快照*。</span><span class="sxs-lookup"><span data-stu-id="46fff-182">By contrast, the referenced assertion calls each operation exactly once, such that it checks that the operations are equal *in a single shot*.</span></span>
<span data-ttu-id="46fff-183">這兩項測試都有助於確保量副程式的正確性。</span><span class="sxs-lookup"><span data-stu-id="46fff-183">Both of these tests are useful in ensuring the correctness of quantum programs.</span></span>


## <a name="further-reading"></a><span data-ttu-id="46fff-184">深入閱讀</span><span class="sxs-lookup"><span data-stu-id="46fff-184">Further Reading</span></span> ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:Microsoft.Quantum.Diagnostics>
