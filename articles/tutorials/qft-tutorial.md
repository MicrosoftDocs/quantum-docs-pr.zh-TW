---
title: 在 Q 中撰寫和模擬 qubit 層級程式#
description: 撰寫和模擬可在個別 qubit 層級運作之配量程式的逐步教學課程
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: 05d3292e1c6e3c8c1163c460f2aaa51c591aa1d5
ms.sourcegitcommit: 8d9d392bf5e114ae223e6f689ba80d25866ff586
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2020
ms.locfileid: "84422235"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="957f5-103">教學課程：在 Q 中撰寫和模擬 qubit 層級程式\#</span><span class="sxs-lookup"><span data-stu-id="957f5-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="957f5-104">歡迎使用量子開發工具組教學課程，以撰寫和模擬可在個別 qubits 上運作的基本配量程式。</span><span class="sxs-lookup"><span data-stu-id="957f5-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="957f5-105">雖然問 # 主要是針對大規模的量副程式建立為高階程式設計語言，但也可以輕鬆地用來探索較低層級的量副程式：直接定址特定的 qubits。</span><span class="sxs-lookup"><span data-stu-id="957f5-105">Although Q# was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="957f5-106">問 # 的彈性可讓使用者從任何這類抽象層處理量子系統，而在本教學課程中，我們會深入探討 qubits 本身。</span><span class="sxs-lookup"><span data-stu-id="957f5-106">The flexibility of Q# allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="957f5-107">具體而言，我們將探討「[量子傅立葉」轉換](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)的幕後，這是許多較大配量演算法不可或缺的副程式。</span><span class="sxs-lookup"><span data-stu-id="957f5-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="957f5-108">請注意，此低層級的配量資訊處理方式通常是以「[量子線路](xref:microsoft.quantum.concepts.circuits)」來描述，這代表將閘道的順序應用到特定的系統 qubits。</span><span class="sxs-lookup"><span data-stu-id="957f5-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="957f5-109">因此，我們依序套用的單一和多 qubit 作業可以在「電路圖」中輕鬆呈現。</span><span class="sxs-lookup"><span data-stu-id="957f5-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="957f5-110">在我們的案例中，我們將定義一個 Q # 作業來執行完整的三 qubit 配量傅立葉轉換，其具有下列標記法做為線路：</span><span class="sxs-lookup"><span data-stu-id="957f5-110">In our case, we will define a Q# operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="957f5-111">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="957f5-111">Prerequisites</span></span>

* <span data-ttu-id="957f5-112">使用您慣用的語言和開發環境來[安裝](xref:microsoft.quantum.install)配量開發工具組。</span><span class="sxs-lookup"><span data-stu-id="957f5-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="957f5-113">如果您已安裝 QDK，請確定您已[更新](xref:microsoft.quantum.update)為最新版本</span><span class="sxs-lookup"><span data-stu-id="957f5-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="957f5-114">在本教學課程中，您將了解如何：</span><span class="sxs-lookup"><span data-stu-id="957f5-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="957f5-115">定義 Q 中的量子作業#</span><span class="sxs-lookup"><span data-stu-id="957f5-115">Define quantum operations in Q#</span></span>
> * <span data-ttu-id="957f5-116">直接從命令列呼叫 Q # 作業，或使用傳統主機程式</span><span class="sxs-lookup"><span data-stu-id="957f5-116">Call Q# operations directly from the command line or using a classical host program</span></span>
> * <span data-ttu-id="957f5-117">模擬從 qubit 配置到測量輸出的量子作業</span><span class="sxs-lookup"><span data-stu-id="957f5-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="957f5-118">觀察量子系統的模擬 wavefunction 在整個作業過程中的演變方式</span><span class="sxs-lookup"><span data-stu-id="957f5-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="957f5-119">使用 Microsoft 的量子開發工具組來執行量副程式，通常是由兩個部分組成：</span><span class="sxs-lookup"><span data-stu-id="957f5-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="957f5-120">程式本身，使用 Q # 量副程式設計語言來執行，然後叫用以在量子電腦或量子模擬器上執行。</span><span class="sxs-lookup"><span data-stu-id="957f5-120">The program itself, which is implemented using the Q# quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="957f5-121">其中包括</span><span class="sxs-lookup"><span data-stu-id="957f5-121">These consist of</span></span> 
    - <span data-ttu-id="957f5-122">Q # 作業：在量子暫存器上作用的副程式，以及</span><span class="sxs-lookup"><span data-stu-id="957f5-122">Q# operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="957f5-123">Q # 函式：在量子演算法內使用的傳統副程式。</span><span class="sxs-lookup"><span data-stu-id="957f5-123">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="957f5-124">用來呼叫量副程式的進入點，並指定應該在其上執行的目的電腦。</span><span class="sxs-lookup"><span data-stu-id="957f5-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="957f5-125">這可以直接從命令列進行，或透過以傳統程式設計語言（例如 Python 或 c #）撰寫的主機程式來完成。</span><span class="sxs-lookup"><span data-stu-id="957f5-125">This can be done directly from the command line, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="957f5-126">本教學課程包含您偏好的任何方法的指示。</span><span class="sxs-lookup"><span data-stu-id="957f5-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="957f5-127">配置 qubits 並定義量子作業</span><span class="sxs-lookup"><span data-stu-id="957f5-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="957f5-128">本教學課程的第一個部分包含定義 Q # 作業，此作業會 `Perform3qubitQFT` 在三個 qubits 上執行量子傅立葉轉換。</span><span class="sxs-lookup"><span data-stu-id="957f5-128">The first part of this tutorial consists of defining the Q# operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="957f5-129">此外，我們將使用函式 [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) 來觀察我們的三個 qubit 系統的模擬 wavefunction 如何在作業之間演變。</span><span class="sxs-lookup"><span data-stu-id="957f5-129">In addition, we will use the [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="957f5-130">第一個步驟是建立您的 Q # 專案和檔案。</span><span class="sxs-lookup"><span data-stu-id="957f5-130">The first step is creating your Q# project and file.</span></span>
<span data-ttu-id="957f5-131">這項操作的步驟取決於您將用來呼叫程式的環境，您可以在個別的[安裝指南](xref:microsoft.quantum.install)中找到詳細資料。</span><span class="sxs-lookup"><span data-stu-id="957f5-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="957f5-132">我們會逐步引導您完成檔案的元件，但此程式碼也會以完整區塊的形式提供。</span><span class="sxs-lookup"><span data-stu-id="957f5-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-q-operations"></a><span data-ttu-id="957f5-133">存取其他 Q # 作業的命名空間</span><span class="sxs-lookup"><span data-stu-id="957f5-133">Namespaces to access other Q# operations</span></span>
<span data-ttu-id="957f5-134">在檔案中，我們會先定義 `NamespaceQFT` 將由編譯器存取的命名空間。</span><span class="sxs-lookup"><span data-stu-id="957f5-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="957f5-135">為了讓我們使用現有的 Q # 作業，我們會開啟相關的 `Microsoft.Quantum.<>` 命名空間。</span><span class="sxs-lookup"><span data-stu-id="957f5-135">For our operation to make use of existing Q# operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="957f5-136">定義具有引數的作業並傳回</span><span class="sxs-lookup"><span data-stu-id="957f5-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="957f5-137">接下來，我們會定義作業 `Perform3qubitQFT` ：</span><span class="sxs-lookup"><span data-stu-id="957f5-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="957f5-138">目前，此作業不會採用任何引數，也不會傳回任何---在此情況下，我們會寫出它傳回的 `Unit` 物件（在 c # 中類似于，而在 Python 中則是 `void` 空的元組） `Tuple[()]` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="957f5-139">稍後，我們會將它修改為傳回測量結果的陣列，此時將會 `Unit` 取代此位置 `Result[]` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="957f5-140">使用配置 qubits`using`</span><span class="sxs-lookup"><span data-stu-id="957f5-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="957f5-141">在我們的 Q # 作業中，我們會先使用語句來配置三個 qubits 的暫存器 `using` ：</span><span class="sxs-lookup"><span data-stu-id="957f5-141">Within our Q# operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="957f5-142">使用 `using` ，qubits 會自動設定在 $ \ket {0} $ 狀態中。</span><span class="sxs-lookup"><span data-stu-id="957f5-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="957f5-143">我們可以使用和來驗證這一點 [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) ，這會將字串和系統的目前狀態列印到主控台。</span><span class="sxs-lookup"><span data-stu-id="957f5-143">We can verify this by using [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) and [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="957f5-144">和函式 `Message(<string>)` `DumpMachine()` （ [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) 分別來自和 [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) ）會直接列印到主控台。</span><span class="sxs-lookup"><span data-stu-id="957f5-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="957f5-145">就像實際的量子計算一樣，Q # 並不允許我們直接存取 qubit 狀態。</span><span class="sxs-lookup"><span data-stu-id="957f5-145">Just like a real quantum computation, Q# does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="957f5-146">不過， `DumpMachine` 如果列印目的電腦的目前狀態，它可以在與完整狀態模擬器搭配使用時，提供用於進行偵錯工具和學習的寶貴見解。</span><span class="sxs-lookup"><span data-stu-id="957f5-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="957f5-147">套用單一 qubit 和受控制的閘道</span><span class="sxs-lookup"><span data-stu-id="957f5-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="957f5-148">接下來，我們會套用組成作業本身的閘道。</span><span class="sxs-lookup"><span data-stu-id="957f5-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="957f5-149">問 # 已包含許多基本配量閘道做為 [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) 命名空間中的作業，但這些不是例外狀況。</span><span class="sxs-lookup"><span data-stu-id="957f5-149">Q# already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="957f5-150">在 Q # 作業中，將會以連續循序執行叫用 callables 的語句。</span><span class="sxs-lookup"><span data-stu-id="957f5-150">Within a Q# operation, the statements invoking callables will of course be executed in sequential order.</span></span>
<span data-ttu-id="957f5-151">因此，第一個要套用的閘道是 [`H`](xref:microsoft.quantum.intrinsic.h) 第一個 qubit 的（Hadamard）：</span><span class="sxs-lookup"><span data-stu-id="957f5-151">Hence, the first gate to apply is the [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="./qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="957f5-152">若要將作業從暫存器（也就是陣列中的單一）套用至特定 qubit， `Qubit` `Qubit[]` 我們會使用標準索引標記法。</span><span class="sxs-lookup"><span data-stu-id="957f5-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="957f5-153">因此，將 [`H`](xref:microsoft.quantum.intrinsic.h) 套用至我們的註冊的第一個 qubit `qs` 會採用下列格式：</span><span class="sxs-lookup"><span data-stu-id="957f5-153">So, applying the [`H`](xref:microsoft.quantum.intrinsic.h) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="957f5-154">除了將 `H` （Hadamard）閘道套用至個別 qubits，QFT 電路主要是由控制的旋轉所組成 [`R1`](xref:microsoft.quantum.intrinsic.r1) 。</span><span class="sxs-lookup"><span data-stu-id="957f5-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations.</span></span>
<span data-ttu-id="957f5-155">一般作業會將 `R1(θ, <qubit>)` qubit 的 $ \ket {0} $ 元件保持不變，同時將 $e ^ {i\theta} $ 的旋轉套用至 $ \ket {1} $ 元件。</span><span class="sxs-lookup"><span data-stu-id="957f5-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="957f5-156">控制的作業</span><span class="sxs-lookup"><span data-stu-id="957f5-156">Controlled operations</span></span>

<span data-ttu-id="957f5-157">問 # 讓在一或多個控制項 qubits 上執行作業的條件變得非常容易。</span><span class="sxs-lookup"><span data-stu-id="957f5-157">Q# makes it extremely easy to condition the execution of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="957f5-158">一般來說，我們只會在呼叫前面加 `Controlled` 上，而作業引數則會變更為：</span><span class="sxs-lookup"><span data-stu-id="957f5-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="957f5-159">`Op(<normal args>)`$ \to $ `Controlled Op([<control qubits>], (<normal args>))` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="957f5-160">請注意，控制項 qubits 必須當做陣列提供，即使它是單一 qubit 也是一樣。</span><span class="sxs-lookup"><span data-stu-id="957f5-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="957f5-161">在之後 `H` ，我們會看到下一個閘道是在 `R1` 第一個 qubit 上作用的閘道（並由第二個/第三個控制）：</span><span class="sxs-lookup"><span data-stu-id="957f5-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="./qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="957f5-162">我們稱之為</span><span class="sxs-lookup"><span data-stu-id="957f5-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="957f5-163">請注意，我們會使用命名空間中的函式 [`PI()`](xref:microsoft.quantum.math.pi) [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) ，以 pi 弧度來定義旋轉。</span><span class="sxs-lookup"><span data-stu-id="957f5-163">Note that we use the [`PI()`](xref:microsoft.quantum.math.pi) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="957f5-164">此外，我們 `Double` 會除以（例如）， `2.0` 因為除以整數 `2` 會擲回類型錯誤。</span><span class="sxs-lookup"><span data-stu-id="957f5-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="957f5-165">`R1(π/2)`和 `R1(π/4)` 相當於 `S` 和 `T` 作業（也是在中 `Microsoft.Quantum.Intrinsic` ）。</span><span class="sxs-lookup"><span data-stu-id="957f5-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="957f5-166">將相關的 `H` 作業和受控制的旋轉套用至第二個和第三個 qubits 之後：</span><span class="sxs-lookup"><span data-stu-id="957f5-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="957f5-167">我們只需要套用網 [`SWAP`](xref:microsoft.quantum.intrinsic.swap) 關來完成線路：</span><span class="sxs-lookup"><span data-stu-id="957f5-167">we need only apply a [`SWAP`](xref:microsoft.quantum.intrinsic.swap) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="957f5-168">這是必要的，因為配量傅立葉轉換的本質會以反向順序輸出 qubits，因此，交換可讓副程式緊密整合成較大的演算法。</span><span class="sxs-lookup"><span data-stu-id="957f5-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="957f5-169">因此，我們已完成將配量傅立葉轉換的 qubit 層級作業寫入我們的 Q # 操作中：</span><span class="sxs-lookup"><span data-stu-id="957f5-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our Q# operation:</span></span>

<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="957f5-170">不過，我們還無法一天呼叫它。</span><span class="sxs-lookup"><span data-stu-id="957f5-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="957f5-171">我們的 qubits 在配置時處於 $ \ket $ 的狀態 {0} ，而且在 Q # 中的運作方式很類似，我們應該以我們找到它們（或更棒）的相同方式來保留專案。</span><span class="sxs-lookup"><span data-stu-id="957f5-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in Q# we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="957f5-172">解除配置 qubits</span><span class="sxs-lookup"><span data-stu-id="957f5-172">Deallocate qubits</span></span>

<span data-ttu-id="957f5-173">我們 [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) 再次呼叫以查看作業後的狀態，最後再套用至 qubit 暫存器， [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) 以在完成作業之前，將 qubits 重設為 $ \ket {0} $：</span><span class="sxs-lookup"><span data-stu-id="957f5-173">We call [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="957f5-174">將所有已解除配置的 qubits 明確設定為 $ \ket {0} $ 是 Q # 的基本功能，因為它可讓其他作業在開始使用相同的 qubits （稀有資源）時，精確地得知其狀態。</span><span class="sxs-lookup"><span data-stu-id="957f5-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of Q#, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="957f5-175">此外，這可確保不會與系統中的任何其他 qubits 光子。</span><span class="sxs-lookup"><span data-stu-id="957f5-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="957f5-176">如果重設不是在配置區塊的結尾執行 `using` ，則會擲回執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="957f5-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="957f5-177">您的完整 Q # 檔案現在看起來應該像這樣：</span><span class="sxs-lookup"><span data-stu-id="957f5-177">Your full Q# file should now look like this:</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


<span data-ttu-id="957f5-178">當 Q # 檔案和作業完成時，我們的配量程式已準備好進行呼叫和模擬。</span><span class="sxs-lookup"><span data-stu-id="957f5-178">With the Q# file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="execute-the-program"></a><span data-ttu-id="957f5-179">執行程式</span><span class="sxs-lookup"><span data-stu-id="957f5-179">Execute the program</span></span>

<span data-ttu-id="957f5-180">在檔案中定義了我們的 Q # 作業之後 `.qs` ，我們現在需要呼叫該作業，並觀察所有傳回的傳統資料。</span><span class="sxs-lookup"><span data-stu-id="957f5-180">Having defined our Q# operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="957f5-181">目前未傳回任何專案（請記得，上述定義的作業會傳回 `Unit` ），但當我們稍後修改 Q # 作業以傳回測量結果陣列（ `Result[]` ）時，我們會解決此問題。</span><span class="sxs-lookup"><span data-stu-id="957f5-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the Q# operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="957f5-182">雖然 Q # 程式在用來呼叫它的環境中很普遍，但執行此動作的方式當然會有所不同。</span><span class="sxs-lookup"><span data-stu-id="957f5-182">While the Q# program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="957f5-183">因此，只需遵循與您的安裝程式相對應的索引標籤中的指示：從 Q # 命令列應用程式運作，或在 Python 或 c # 中使用主機程式。</span><span class="sxs-lookup"><span data-stu-id="957f5-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the Q# command line application or using a host program in Python or C#.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="957f5-184">命令列</span><span class="sxs-lookup"><span data-stu-id="957f5-184">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="957f5-185">從命令列執行 Q # 程式，只需要稍微變更 Q # 檔案。</span><span class="sxs-lookup"><span data-stu-id="957f5-185">Running the Q# program from the command line requires only a small change to the Q# file.</span></span>

<span data-ttu-id="957f5-186">只要加 `@EntryPoint()` 到作業定義前面的一行：</span><span class="sxs-lookup"><span data-stu-id="957f5-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="957f5-187">若要執行程式，請開啟專案資料夾中的終端機，並輸入</span><span class="sxs-lookup"><span data-stu-id="957f5-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="957f5-188">執行時，您應該會 `Message` `DumpMachine` 在主控台中看到下列輸出。</span><span class="sxs-lookup"><span data-stu-id="957f5-188">Upon execution, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="957f5-189">Python</span><span class="sxs-lookup"><span data-stu-id="957f5-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="957f5-190">建立 Python 主機檔案： `host.py` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="957f5-191">主機檔案的結構如下所示：</span><span class="sxs-lookup"><span data-stu-id="957f5-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="957f5-192">首先，我們會匯入 `qsharp` 模組，以註冊 Q # 互通性的模組載入器。</span><span class="sxs-lookup"><span data-stu-id="957f5-192">First, we import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="957f5-193">這可讓問 # 命名空間（例如 `NamespaceQFT` 我們在 Q # 檔案中定義的）顯示為 Python 模組，我們可以從中匯入 Q # 作業。</span><span class="sxs-lookup"><span data-stu-id="957f5-193">This allows Q# namespaces (e.g. the `NamespaceQFT` we defined in our Q# file) to appear as Python modules, from which we can import Q# operations.</span></span>
2. <span data-ttu-id="957f5-194">然後，匯入我們會直接叫用---的 Q # 作業，在此案例中為 `Perform3qubitQFT` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-194">Then, import the Q# operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="957f5-195">我們只需要將進入點匯入 Q # 程式中（也就是_不_ `H` 是像是和的作業 `R1` ，由其他 Q # 作業呼叫，但傳統主機絕不會呼叫）。</span><span class="sxs-lookup"><span data-stu-id="957f5-195">We need only import the entry point into a Q# program (i.e. _not_ operations like `H` and `R1`, which are called by other Q# operations but never by the classical host).</span></span>
3. <span data-ttu-id="957f5-196">在模擬 Q # 作業或函數時，請使用表單在 `<Q#callable>.simulate(<args>)` `QuantumSimulator()` 目的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="957f5-196">In simulating Q# operations or functions, use the form `<Q#callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="957f5-197">如果我們想要在不同的電腦上呼叫作業，例如 `ResourceEstimator()` ，我們只會使用 `<Q#callable>.estimate_resources(<args>)` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<Q#callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="957f5-198">一般來說，問 # 作業與執行所在的機器無關，但某些功能（例如） `DumpMachine` 可能會有不同的行為。</span><span class="sxs-lookup"><span data-stu-id="957f5-198">In general, Q# operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="957f5-199">執行模擬時，作業呼叫會傳回 Q # 檔案中定義的值。</span><span class="sxs-lookup"><span data-stu-id="957f5-199">Upon performing the simulation, the operation call will return values as defined in the Q# file.</span></span>
    <span data-ttu-id="957f5-200">現在不會傳回任何內容，但稍後我們會看到指派和處理這些值的範例。</span><span class="sxs-lookup"><span data-stu-id="957f5-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="957f5-201">透過我們手中的結果資料，並以完全傳統的方式進行，我們就可以執行任何想要的動作。</span><span class="sxs-lookup"><span data-stu-id="957f5-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="957f5-202">您的完整檔案應如下所 `host.py` 示：</span><span class="sxs-lookup"><span data-stu-id="957f5-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="957f5-203">執行 Python 檔案，並在您的主控台中列印，您應該會在 `Message` 下方看到和 `DumpMachine` 輸出。</span><span class="sxs-lookup"><span data-stu-id="957f5-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="957f5-204">C#</span><span class="sxs-lookup"><span data-stu-id="957f5-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="957f5-205">遵循[安裝指南](xref:microsoft.quantum.install.cs)中的相同指示，建立 c # 主機檔案，並將它重新命名為 `host.cs` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="957f5-206">C # 主機有四個部分：</span><span class="sxs-lookup"><span data-stu-id="957f5-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="957f5-207">建構量子模擬器。</span><span class="sxs-lookup"><span data-stu-id="957f5-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="957f5-208">在下列程式碼中，這是變數 `qsim` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="957f5-209">計算量子演算法所需的任何引數。</span><span class="sxs-lookup"><span data-stu-id="957f5-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="957f5-210">此範例中沒有任何內容。</span><span class="sxs-lookup"><span data-stu-id="957f5-210">There are none in this example.</span></span>
3. <span data-ttu-id="957f5-211">執行量子演算法。</span><span class="sxs-lookup"><span data-stu-id="957f5-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="957f5-212">每個 Q# 作業都會產生一個具有相同名稱的 C# 類別。</span><span class="sxs-lookup"><span data-stu-id="957f5-212">Each Q# operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="957f5-213">此類別具有 `Run` 方法，會以**非同步方式**執行作業。</span><span class="sxs-lookup"><span data-stu-id="957f5-213">This class has a `Run` method that **asynchronously** executes the operation.</span></span>
    <span data-ttu-id="957f5-214">執行是非同步的，因為實際硬體的執行將是非同步的。</span><span class="sxs-lookup"><span data-stu-id="957f5-214">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="957f5-215">因為 `Run` 方法是非同步，所以我們會呼叫 `Wait()` 方法，這會封鎖執行直到工作完成，並以同步方式傳回結果。</span><span class="sxs-lookup"><span data-stu-id="957f5-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks execution until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="957f5-216">處理傳回的作業結果。</span><span class="sxs-lookup"><span data-stu-id="957f5-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="957f5-217">目前，此作業不會傳回任何內容。</span><span class="sxs-lookup"><span data-stu-id="957f5-217">For now, the operation returns nothing.</span></span>


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
<span data-ttu-id="957f5-218">執行應用程式，您的輸出應該會符合以下的結果。</span><span class="sxs-lookup"><span data-stu-id="957f5-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="957f5-219">當您按下按鍵後，程式就會結束。</span><span class="sxs-lookup"><span data-stu-id="957f5-219">The program will exit after you press a key.</span></span>
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

<span data-ttu-id="957f5-220">在完整狀態模擬器上呼叫時，會 `DumpMachine()` 提供量子狀態 wavefunction 的多個標記法。</span><span class="sxs-lookup"><span data-stu-id="957f5-220">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="957f5-221">$N $-qubit 系統的可能狀態可以用 $ 2 ^ n $ 計算基礎狀態表示，每一個都有對應的複雜係數（只是波幅和一個階段）。</span><span class="sxs-lookup"><span data-stu-id="957f5-221">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="957f5-222">計算基礎狀態會對應到長度 $n $---的所有可能二進位字串，也就是 qubit 狀態 $ \ket {0} $ 和 $ \ket $ 的所有可能組合 {1} ，其中每個二進位數位都會對應至個別的 qubit。</span><span class="sxs-lookup"><span data-stu-id="957f5-222">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="957f5-223">第一個資料列會以其重大順序提供批註，其中包含對應 qubits 的識別碼。</span><span class="sxs-lookup"><span data-stu-id="957f5-223">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="957f5-224">Qubit 是「 `2` 最重要」的意思，就是在基礎狀態向量 $ \ket{i} $ 的二進位標記法中，Qubit 的狀態會 `2` 對應到最左邊的數位。</span><span class="sxs-lookup"><span data-stu-id="957f5-224">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="957f5-225">例如，$ \ket {6} = \ket {110} $ 包含 qubits `2` ，以及 $ `1` \ket {1} $ 和 qubit `0` in $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="957f5-225">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="957f5-226">其餘的資料列會以笛卡和極座標格式來描述測量基礎狀態向量 $ \ket{i} $ 的機率幅度。</span><span class="sxs-lookup"><span data-stu-id="957f5-226">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="957f5-227">輸入狀態 $ \ket $ 的第一列詳細資料 {000} ：</span><span class="sxs-lookup"><span data-stu-id="957f5-227">In detail for the first row of our input state $\ket{000}$:</span></span>
* <span data-ttu-id="957f5-228">**`|0>:`** 這個資料列會對應到 `0` 計算基礎狀態（假設我們的初始狀態是 $ \ket {000} $，我們預期這是唯一的狀態，也就是機率振幅）。</span><span class="sxs-lookup"><span data-stu-id="957f5-228">**`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="957f5-229">**`1.000000 +  0.000000 i`**：笛卡爾格式的機率幅度。</span><span class="sxs-lookup"><span data-stu-id="957f5-229">**`1.000000 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="957f5-230">**` == `**： `equal` 符號會分隔兩個對等的標記法。</span><span class="sxs-lookup"><span data-stu-id="957f5-230">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="957f5-231">**`********************`**：大小的圖形表示，的數目與 `*` 測量此狀態向量的機率成正比。</span><span class="sxs-lookup"><span data-stu-id="957f5-231">**`********************`**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="957f5-232">**`[ 1.000000 ]`**：量值的數值</span><span class="sxs-lookup"><span data-stu-id="957f5-232">**`[ 1.000000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="957f5-233">**`    ---`**：振幅階段的圖形表示。</span><span class="sxs-lookup"><span data-stu-id="957f5-233">**`    ---`**: A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="957f5-234">**`[ 0.0000 rad ]`**：階段的數值（以弧度為單位）。</span><span class="sxs-lookup"><span data-stu-id="957f5-234">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="957f5-235">大小和階段都會以圖形標記法顯示。</span><span class="sxs-lookup"><span data-stu-id="957f5-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="957f5-236">量值的表示方式很簡單：它會顯示的橫條 `*` ，而機率越高，橫條就越大。</span><span class="sxs-lookup"><span data-stu-id="957f5-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="957f5-237">針對階段，請參閱[測試和偵錯工具：](xref:microsoft.quantum.guide.testingdebugging#dump-functions)根據角度範圍的可能符號表示傾印函式。</span><span class="sxs-lookup"><span data-stu-id="957f5-237">For the phase, see [Testing and debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="957f5-238">因此，列印的輸出會說明我們的程式設計閘道已將我們的狀態轉換為</span><span class="sxs-lookup"><span data-stu-id="957f5-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="957f5-239">$ $ \ket{\psi} \_ {初始值} = \ket {000} $ $</span><span class="sxs-lookup"><span data-stu-id="957f5-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="957f5-240">to</span><span class="sxs-lookup"><span data-stu-id="957f5-240">to</span></span> 

<span data-ttu-id="957f5-241">$ $ \begin{align} \ket{\psi} \_ {final} &= \frac {1} {\sqrt {8} } \left （\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right） \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}，\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="957f5-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="957f5-242">這正是 qubit 傅立葉轉換的行為。</span><span class="sxs-lookup"><span data-stu-id="957f5-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="957f5-243">如果您想知道其他輸入狀態受到影響的方式，建議您在轉換之前，先套用 qubit 作業。</span><span class="sxs-lookup"><span data-stu-id="957f5-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="957f5-244">新增測量</span><span class="sxs-lookup"><span data-stu-id="957f5-244">Adding measurements</span></span>

<span data-ttu-id="957f5-245">可惜的是，配量機制的基石告訴我們，實際的量子系統不能有這種 `DumpMachine` 功能。</span><span class="sxs-lookup"><span data-stu-id="957f5-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="957f5-246">相反地，我們會強制透過測量來解壓縮資訊，這通常不會使我們無法提供完整的量子狀態，而且也可以大幅改變系統本身。</span><span class="sxs-lookup"><span data-stu-id="957f5-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="957f5-247">配量測量有許多種，但我們會將焦點放在單一 qubits 上最基本的： projective 測量。</span><span class="sxs-lookup"><span data-stu-id="957f5-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="957f5-248">根據給定的測量單位（例如計算基礎 $ \{ \ket {0} 、\ket {1} \} $），qubit 狀態會投射到測量的任何基礎狀態---因此會摧毀兩者之間的任何重迭。</span><span class="sxs-lookup"><span data-stu-id="957f5-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="957f5-249">為了在 Q # 程式中執行測量，我們使用作業 `M` （來自 `Microsoft.Quantum.Intrinsic` ），它會傳回 `Result` 型別。</span><span class="sxs-lookup"><span data-stu-id="957f5-249">To implement measurements within a Q# program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="957f5-250">首先，我們會修改作業 `Perform3QubitQFT` 以傳回測量結果的陣列， `Result[]` 而不是 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="957f5-251">定義和初始化 `Result[]` 陣列</span><span class="sxs-lookup"><span data-stu-id="957f5-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="957f5-252">在配置 qubits 之前（也就是在 `using` 語句之前），我們會宣告並系結此長度為3的陣列（ `Result` 每個 qubit 一個）：</span><span class="sxs-lookup"><span data-stu-id="957f5-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="957f5-253">`mutable`關鍵字前面 `resultArray` 允許稍後在程式碼中重新系結變數---例如，新增測量結果時。</span><span class="sxs-lookup"><span data-stu-id="957f5-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="957f5-254">在迴圈中執行測量 `for` ，並將結果新增至陣列</span><span class="sxs-lookup"><span data-stu-id="957f5-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="957f5-255">在區塊內的傅立葉轉換作業之後 `using` ，插入下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="957f5-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="957f5-256">[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)在陣列上呼叫的函式（例如，我們的 qubits 陣列 `qs` ）會傳回陣列索引上方的範圍。</span><span class="sxs-lookup"><span data-stu-id="957f5-256">The [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="957f5-257">在這裡，我們會在迴圈中使用它 `for` 來依序使用語句來測量每個 qubit `M(qs[i])` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="957f5-258">然後，每個測量的 `Result` 類型（ `Zero` 或 `One` ）都會 `resultArray` 使用 update 和-重新指派語句加入至中的對應索引位置。</span><span class="sxs-lookup"><span data-stu-id="957f5-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="957f5-259">此語句的語法對 Q # 而言是唯一的，但會對應到 `resultArray[i] <- M(qs[i])` 在其他語言（例如 F # 和 R）中所看到的類似變數重新指派。</span><span class="sxs-lookup"><span data-stu-id="957f5-259">The syntax of this statement is unique to Q#, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="957f5-260">關鍵字 `set` 一律用來重新指派使用系結的變數 `mutable` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="957f5-261">退貨`resultArray`</span><span class="sxs-lookup"><span data-stu-id="957f5-261">Return `resultArray`</span></span>

<span data-ttu-id="957f5-262">所有三個 qubits 都經過測量並將結果新增至 `resultArray` 之後，我們就可以像之前一樣安全地重設和解除配置 qubits。</span><span class="sxs-lookup"><span data-stu-id="957f5-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="957f5-263">在 `using` 區塊的關閉之後，插入</span><span class="sxs-lookup"><span data-stu-id="957f5-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="957f5-264">最後傳回作業的輸出。</span><span class="sxs-lookup"><span data-stu-id="957f5-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="957f5-265">瞭解測量的效果</span><span class="sxs-lookup"><span data-stu-id="957f5-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="957f5-266">讓我們變更函式的位置 `DumpMachine` ，以輸出測量前後的狀態。</span><span class="sxs-lookup"><span data-stu-id="957f5-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="957f5-267">最後的作業程式碼看起來應該像這樣：</span><span class="sxs-lookup"><span data-stu-id="957f5-267">The final operation code should look like:</span></span> 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

<span data-ttu-id="957f5-268">如果您是從命令列工作，傳回的陣列只會在執行結束時直接列印到主控台。</span><span class="sxs-lookup"><span data-stu-id="957f5-268">If you are working from the command line, the returned array will simply be printed directly to the console at the end of the execution.</span></span>
<span data-ttu-id="957f5-269">否則，請更新您的主機程式，以處理傳回的陣列。</span><span class="sxs-lookup"><span data-stu-id="957f5-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="957f5-270">命令列</span><span class="sxs-lookup"><span data-stu-id="957f5-270">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="957f5-271">若要更瞭解將在主控台中列印的傳回陣列，我們可以 `Message` 在語句之前的 Q # 檔案中新增另一個 `return` ：</span><span class="sxs-lookup"><span data-stu-id="957f5-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the Q# file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="957f5-272">執行專案，您的輸出看起來應該像下面這樣：</span><span class="sxs-lookup"><span data-stu-id="957f5-272">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[<span data-ttu-id="957f5-273">Python</span><span class="sxs-lookup"><span data-stu-id="957f5-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="957f5-274">將您的 Python 程式更新為下列專案：</span><span class="sxs-lookup"><span data-stu-id="957f5-274">Update your Python program to the following:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

<span data-ttu-id="957f5-275">執行檔案，您的輸出看起來應該像下面這樣：</span><span class="sxs-lookup"><span data-stu-id="957f5-275">Run the file, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[<span data-ttu-id="957f5-276">C#</span><span class="sxs-lookup"><span data-stu-id="957f5-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="957f5-277">現在，我們的作業會傳回結果，請將方法呼叫取代 `Wait()` 為提取 `Result` 屬性。</span><span class="sxs-lookup"><span data-stu-id="957f5-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="957f5-278">這仍然可以達成稍早所討論的相同同步性，而且我們可以直接將此值系結至變數 `measurementResult` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="957f5-279">執行專案，您的輸出看起來應該像下面這樣：</span><span class="sxs-lookup"><span data-stu-id="957f5-279">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

<span data-ttu-id="957f5-280">此輸出說明一些不同的事項：</span><span class="sxs-lookup"><span data-stu-id="957f5-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="957f5-281">比較傳回的結果與預先測量 `DumpMachine` ，顯然不會說明 QFT _not_後重迭的基礎狀態。</span><span class="sxs-lookup"><span data-stu-id="957f5-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="957f5-282">測量只會傳回單一的基礎狀態，其機率取決於系統 wavefunction 中該狀態的振幅。</span><span class="sxs-lookup"><span data-stu-id="957f5-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="957f5-283">從後續測量開始 `DumpMachine` ，我們看到量值會_變更_狀態本身，並將其從初始重迭的基礎狀態投射到對應至測量值的單一基礎狀態。</span><span class="sxs-lookup"><span data-stu-id="957f5-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="957f5-284">如果我們多次重複此作業，我們會看到結果統計資料開始說明 QFT 後狀態的平均加權重迭，讓每個快照的隨機結果增加。</span><span class="sxs-lookup"><span data-stu-id="957f5-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="957f5-285">_不過_，除了效率不佳而且仍然完美，這只會重現基礎狀態的相對 amplitudes，而不是兩者之間的相對階段。</span><span class="sxs-lookup"><span data-stu-id="957f5-285">_However_, besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="957f5-286">在此範例中，後者不是問題，但如果 QFT 的輸入比 $ \ket $ 更複雜，我們會看到相對階段出現 {000} 。</span><span class="sxs-lookup"><span data-stu-id="957f5-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="957f5-287">部分測量</span><span class="sxs-lookup"><span data-stu-id="957f5-287">Partial measurements</span></span> 
<span data-ttu-id="957f5-288">若要探索如何只測量暫存器的某些 qubits 可能會影響系統狀態，請嘗試在測量線之後將下列程式碼新增至 `for` 迴圈內：</span><span class="sxs-lookup"><span data-stu-id="957f5-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="957f5-289">請注意，若要存取函式， `IntAsString` 您必須新增</span><span class="sxs-lookup"><span data-stu-id="957f5-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="957f5-290">加上命名空間語句的其餘部分 `open` 。</span><span class="sxs-lookup"><span data-stu-id="957f5-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="957f5-291">在產生的輸出中，您會在測量每個 qubit 時，看到逐漸投射到 subspaces 中。</span><span class="sxs-lookup"><span data-stu-id="957f5-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-q-libraries"></a><span data-ttu-id="957f5-292">使用 Q # 程式庫</span><span class="sxs-lookup"><span data-stu-id="957f5-292">Use the Q# libraries</span></span>
<span data-ttu-id="957f5-293">如我們在簡介中所述，我們有許多問 # 的威力在於它可讓您抽象化處理個別 qubits 的擔心。</span><span class="sxs-lookup"><span data-stu-id="957f5-293">As we mentioned in the introduction, much of Q#'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="957f5-294">事實上，如果您想要開發完整規模、適用的量副程式，請擔心作業是在 `H` 特定旋轉之前或之後才會變慢。</span><span class="sxs-lookup"><span data-stu-id="957f5-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="957f5-295">Q # 程式庫包含[QFT](xref:microsoft.quantum.canon.qft)作業，您可以直接採用並申請任何數目的 qubits。</span><span class="sxs-lookup"><span data-stu-id="957f5-295">The Q# libraries contain the [QFT](xref:microsoft.quantum.canon.qft) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="957f5-296">若要試試看，請在您的 Q # 檔案中定義具有相同內容的新作業 `Perform3QubitQFT` ，但從第一個到的所有內容都是 `H` `SWAP` 由兩個簡單的程式程式碼所取代：</span><span class="sxs-lookup"><span data-stu-id="957f5-296">To give it a try, define a new operation in your Q# file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="957f5-297">第一行只 [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) 會建立 qubits 的已配置陣列運算式， `qs` 這就是[QFT](xref:microsoft.quantum.canon.qft)作業做為引數所採用的方式。</span><span class="sxs-lookup"><span data-stu-id="957f5-297">The first line simply creates a [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:microsoft.quantum.canon.qft) operation takes as an argument.</span></span>
<span data-ttu-id="957f5-298">這會對應到註冊中 qubits 的索引順序。</span><span class="sxs-lookup"><span data-stu-id="957f5-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="957f5-299">若要存取這些作業，請 `open` 在 Q # 檔案開頭新增其個別命名空間的語句：</span><span class="sxs-lookup"><span data-stu-id="957f5-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the Q# file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="957f5-300">現在，請調整您的主機程式，以呼叫新作業的名稱（例如 `PerformIntrinsicQFT` ），並為它提供 whirl。</span><span class="sxs-lookup"><span data-stu-id="957f5-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="957f5-301">若要查看使用 Q # 程式庫作業的實際優點，請將 qubits 的數目變更為以外的值 `3` ：</span><span class="sxs-lookup"><span data-stu-id="957f5-301">To see the real benefit of using the Q# library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="957f5-302">因此，您可以將適當的 QFT 套用到任何指定的 qubits 數目，而不必擔心新 `H` 作業和每個 qubit 的旋轉。</span><span class="sxs-lookup"><span data-stu-id="957f5-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="957f5-303">請注意，當您增加---qubits 數目時，配量模擬器會以指數方式執行較長的時間，因為我們會期待到真正的量子硬體。</span><span class="sxs-lookup"><span data-stu-id="957f5-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>













