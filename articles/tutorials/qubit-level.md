---
title: '撰寫和模擬中的量子位層級程式 :::no-loc(Q#):::'
description: 撰寫和模擬在個別量子位層級運作之量副程式的逐步教學課程
author: gillenhaalb
ms.author: a-gibec
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 1bb66ae0fe7de785c417b0bef480e52adea5534d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691717"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="2ff65-103">教學課程：在 Q 中撰寫和模擬量子位層級程式\#</span><span class="sxs-lookup"><span data-stu-id="2ff65-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="2ff65-104">歡迎使用量子開發工具組教學課程，以撰寫和模擬在個別量子位上運作的基本量副程式。</span><span class="sxs-lookup"><span data-stu-id="2ff65-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="2ff65-105">雖然 :::no-loc(Q#)::: 主要是建立為大規模量副程式的高階程式設計語言，但它可以輕鬆地用來探索較低層級的量副程式：直接定址特定的量子位。</span><span class="sxs-lookup"><span data-stu-id="2ff65-105">Although :::no-loc(Q#)::: was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="2ff65-106">的彈性 :::no-loc(Q#)::: 可讓使用者從任何這類抽象層處理量子系統，在本教學課程中，我們會深入探討量子位本身。</span><span class="sxs-lookup"><span data-stu-id="2ff65-106">The flexibility of :::no-loc(Q#)::: allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="2ff65-107">具體而言，我們會看看 [量子傅立葉轉換](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)的本質，這是許多較大型量子演算法不可或缺的副程式。</span><span class="sxs-lookup"><span data-stu-id="2ff65-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="2ff65-108">請注意，此量子資訊處理的低層級視圖通常是以「[量子線路](xref:microsoft.quantum.concepts.circuits)」來描述，這代表系統的特定量子位之閘道的順序應用。</span><span class="sxs-lookup"><span data-stu-id="2ff65-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="2ff65-109">因此，我們順序套用的單一和多量子位作業，可以立即以「電路圖」表示。</span><span class="sxs-lookup"><span data-stu-id="2ff65-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="2ff65-110">在我們的案例中，我們將定義一項作業 :::no-loc(Q#)::: 來執行完整的三量子位量子傅立葉轉換，其以下列標記法作為電路：</span><span class="sxs-lookup"><span data-stu-id="2ff65-110">In our case, we will define a :::no-loc(Q#)::: operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="2ff65-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="2ff65-111">Prerequisites</span></span>

* <span data-ttu-id="2ff65-112">使用您慣用的語言和開發環境，[安裝](xref:microsoft.quantum.install)量子開發工具組。</span><span class="sxs-lookup"><span data-stu-id="2ff65-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="2ff65-113">如果您已安裝 QDK，請確定您已[更新](xref:microsoft.quantum.update)為最新版本</span><span class="sxs-lookup"><span data-stu-id="2ff65-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="2ff65-114">在本教學課程中，您將了解如何：</span><span class="sxs-lookup"><span data-stu-id="2ff65-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="2ff65-115">定義中的量子作業 :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="2ff65-115">Define quantum operations in :::no-loc(Q#):::</span></span>
> * <span data-ttu-id="2ff65-116">:::no-loc(Q#):::從命令提示字元或使用傳統主機程式直接呼叫作業</span><span class="sxs-lookup"><span data-stu-id="2ff65-116">Call :::no-loc(Q#)::: operations directly from the command prompt or using a classical host program</span></span>
> * <span data-ttu-id="2ff65-117">模擬從量子位配置到測量輸出的量子運算</span><span class="sxs-lookup"><span data-stu-id="2ff65-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="2ff65-118">觀察量子系統的模擬 wavefunction 如何在整個作業中演進</span><span class="sxs-lookup"><span data-stu-id="2ff65-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="2ff65-119">使用 Microsoft 的量子開發工具組執行量副程式通常是由兩個部分所組成：</span><span class="sxs-lookup"><span data-stu-id="2ff65-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="2ff65-120">程式本身，它會使用 :::no-loc(Q#)::: 量副程式設計語言來執行，然後叫用以在量子電腦或量子模擬器上執行。</span><span class="sxs-lookup"><span data-stu-id="2ff65-120">The program itself, which is implemented using the :::no-loc(Q#)::: quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="2ff65-121">這些包含</span><span class="sxs-lookup"><span data-stu-id="2ff65-121">These consist of</span></span> 
    - <span data-ttu-id="2ff65-122">:::no-loc(Q#)::: 作業：在量子暫存器上作用的副程式，以及</span><span class="sxs-lookup"><span data-stu-id="2ff65-122">:::no-loc(Q#)::: operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="2ff65-123">:::no-loc(Q#)::: 函數：量子演算法內使用的傳統副程式。</span><span class="sxs-lookup"><span data-stu-id="2ff65-123">:::no-loc(Q#)::: functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="2ff65-124">用來呼叫量副程式的進入點，並指定應該在其上執行的目的電腦。</span><span class="sxs-lookup"><span data-stu-id="2ff65-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="2ff65-125">這可以直接從命令提示字元執行，或透過以傳統程式設計語言（例如 Python 或 c #）撰寫的主機程式來完成。</span><span class="sxs-lookup"><span data-stu-id="2ff65-125">This can be done directly from the command prompt, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="2ff65-126">本教學課程包含您偏好之任何方法的指示。</span><span class="sxs-lookup"><span data-stu-id="2ff65-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="2ff65-127">配置量子位並定義量子作業</span><span class="sxs-lookup"><span data-stu-id="2ff65-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="2ff65-128">本教學課程的第一個部分包含定義作業，此作業會 :::no-loc(Q#)::: `Perform3qubitQFT` 在三個量子位上執行量子傅立葉轉換。</span><span class="sxs-lookup"><span data-stu-id="2ff65-128">The first part of this tutorial consists of defining the :::no-loc(Q#)::: operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="2ff65-129">此外，我們將使用函式 [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) 來觀察三個量子位系統的模擬 wavefunction 如何在整個作業中演進。</span><span class="sxs-lookup"><span data-stu-id="2ff65-129">In addition, we will use the [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="2ff65-130">第一個步驟是建立您的 :::no-loc(Q#)::: 專案和檔案。</span><span class="sxs-lookup"><span data-stu-id="2ff65-130">The first step is creating your :::no-loc(Q#)::: project and file.</span></span>
<span data-ttu-id="2ff65-131">這項操作的步驟取決於您將用來呼叫程式的環境，而且您可以在個別的 [安裝指南](xref:microsoft.quantum.install)中找到詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2ff65-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="2ff65-132">我們會逐步引導您完成檔案的元件，但是程式碼也是以完整區塊的形式提供。</span><span class="sxs-lookup"><span data-stu-id="2ff65-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-no-locq-operations"></a><span data-ttu-id="2ff65-133">存取其他作業的命名空間 :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="2ff65-133">Namespaces to access other :::no-loc(Q#)::: operations</span></span>
<span data-ttu-id="2ff65-134">在檔案中，我們會先定義 `NamespaceQFT` 編譯器將存取的命名空間。</span><span class="sxs-lookup"><span data-stu-id="2ff65-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="2ff65-135">為了讓我們的作業使用現有的 :::no-loc(Q#)::: 作業，我們開啟了相關的 `Microsoft.Quantum.<>` 命名空間。</span><span class="sxs-lookup"><span data-stu-id="2ff65-135">For our operation to make use of existing :::no-loc(Q#)::: operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="2ff65-136">使用引數和傳回來定義作業</span><span class="sxs-lookup"><span data-stu-id="2ff65-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="2ff65-137">接下來，我們會定義作業 `Perform3qubitQFT` ：</span><span class="sxs-lookup"><span data-stu-id="2ff65-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="2ff65-138">目前，此作業不會採用任何引數，也不會傳回任何---在此案例中，我們會撰寫它 `Unit` 會傳回類似于 `void` c # 中的物件，或在 Python 中為空的元組 `Tuple[()]` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="2ff65-139">稍後，我們會將它修改為傳回測量結果的陣列，此時將會 `Unit` 由取代 `Result[]` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="2ff65-140">配置量子位 `using`</span><span class="sxs-lookup"><span data-stu-id="2ff65-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="2ff65-141">在我們 :::no-loc(Q#)::: 的作業中，我們會先使用語句配置三個量子位的註冊 `using` ：</span><span class="sxs-lookup"><span data-stu-id="2ff65-141">Within our :::no-loc(Q#)::: operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="2ff65-142">使用時 `using` ，量子位會自動以 $ \ket {0} $ 狀態進行配置。</span><span class="sxs-lookup"><span data-stu-id="2ff65-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="2ff65-143">我們可以使用和來確認這一點 [`Message(<string>)`](xref:Microsoft.Quantum.Intrinsic.Message) [`DumpMachine()`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) ，這會將字串和系統的目前狀態列印到主控台。</span><span class="sxs-lookup"><span data-stu-id="2ff65-143">We can verify this by using [`Message(<string>)`](xref:Microsoft.Quantum.Intrinsic.Message) and [`DumpMachine()`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="2ff65-144">和函式 `Message(<string>)` `DumpMachine()` (自 [`Microsoft.Quantum.Intrinsic`](xref:Microsoft.Quantum.Intrinsic) 和 [`Microsoft.Quantum.Diagnostics`](xref:Microsoft.Quantum.Diagnostics) ，分別) 會直接列印到主控台。</span><span class="sxs-lookup"><span data-stu-id="2ff65-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:Microsoft.Quantum.Diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="2ff65-145">就像實際的量子運算一樣， :::no-loc(Q#)::: 無法讓我們直接存取量子位狀態。</span><span class="sxs-lookup"><span data-stu-id="2ff65-145">Just like a real quantum computation, :::no-loc(Q#)::: does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="2ff65-146">不過，由於會 `DumpMachine` 列印目的電腦的目前狀態，它可以提供在搭配完整狀態模擬器使用時進行偵錯工具和學習的寶貴見解。</span><span class="sxs-lookup"><span data-stu-id="2ff65-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="2ff65-147">套用單一量子位和控制的閘道</span><span class="sxs-lookup"><span data-stu-id="2ff65-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="2ff65-148">接下來，我們會套用組成作業本身的閘道。</span><span class="sxs-lookup"><span data-stu-id="2ff65-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="2ff65-149">:::no-loc(Q#)::: 已包含許多基本量子閘道作為命名空間中的作業 [`Microsoft.Quantum.Intrinsic`](xref:Microsoft.Quantum.Intrinsic) ，而且這些不是例外狀況。</span><span class="sxs-lookup"><span data-stu-id="2ff65-149">:::no-loc(Q#)::: already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:Microsoft.Quantum.Intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="2ff65-150">在作業中 :::no-loc(Q#)::: ，叫用 callables 的語句當然會依序執行。</span><span class="sxs-lookup"><span data-stu-id="2ff65-150">Within a :::no-loc(Q#)::: operation, the statements invoking callables will, of course, be run in sequential order.</span></span>
<span data-ttu-id="2ff65-151">因此，第一個要套用的閘道是 [`H`](xref:Microsoft.Quantum.Intrinsic.H) 第一個量子位的 (Hadamard) ：</span><span class="sxs-lookup"><span data-stu-id="2ff65-151">Hence, the first gate to apply is the [`H`](xref:Microsoft.Quantum.Intrinsic.H) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="2ff65-152">若要 (從登錄將作業套用至特定量子位，也就是 `Qubit` 從陣列中的單一 `Qubit[]`) 我們使用標準索引標記法。</span><span class="sxs-lookup"><span data-stu-id="2ff65-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="2ff65-153">因此，將 [`H`](xref:Microsoft.Quantum.Intrinsic.H) 套用至我們的註冊的第一個量子位 `qs` 會採用下列格式：</span><span class="sxs-lookup"><span data-stu-id="2ff65-153">So, applying the [`H`](xref:Microsoft.Quantum.Intrinsic.H) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="2ff65-154">除了將 `H` (Hadamard) 閘道套用至個別量子位，QFT 電路主要是由受控制的旋轉所組成 [`R1`](xref:Microsoft.Quantum.Intrinsic.R1) 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:Microsoft.Quantum.Intrinsic.R1) rotations.</span></span>
<span data-ttu-id="2ff65-155">一般作業會將 `R1(θ, <qubit>)` 量子位的 $ \ket {0} $ 元件保持不變，同時將 $e ^ {i\theta} $ 的旋轉套用至 $ \ket {1} $ 元件。</span><span class="sxs-lookup"><span data-stu-id="2ff65-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="2ff65-156">控制的作業</span><span class="sxs-lookup"><span data-stu-id="2ff65-156">Controlled operations</span></span>

<span data-ttu-id="2ff65-157">:::no-loc(Q#)::: 讓您在一或多個控制項量子位上執行作業時非常容易。</span><span class="sxs-lookup"><span data-stu-id="2ff65-157">:::no-loc(Q#)::: makes it extremely easy to condition the run of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="2ff65-158">一般而言，我們只是在呼叫前面加 `Controlled` 上，而作業引數的變更如下：</span><span class="sxs-lookup"><span data-stu-id="2ff65-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="2ff65-159">`Op(<normal args>)` $ \to $ `Controlled Op([<control qubits>], (<normal args>))` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="2ff65-160">請注意，您必須以陣列形式提供控制項量子位，即使它是單一量子位也一樣。</span><span class="sxs-lookup"><span data-stu-id="2ff65-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="2ff65-161">之後 `H` ，我們會看到下一個閘道是 `R1` 在第一個量子位 (的閘道，並由第二個/第三個) 控制：</span><span class="sxs-lookup"><span data-stu-id="2ff65-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="2ff65-162">我們稱之為</span><span class="sxs-lookup"><span data-stu-id="2ff65-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="2ff65-163">請注意，我們會使用 [`PI()`](xref:Microsoft.Quantum.Math.PI) 來自命名空間的函式 [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) ，以 pi 弧度來定義旋轉。</span><span class="sxs-lookup"><span data-stu-id="2ff65-163">Note that we use the [`PI()`](xref:Microsoft.Quantum.Math.PI) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="2ff65-164">此外，我們 `Double` 會除以 (例如) ， `2.0` 因為除以整數 `2` 會擲回類型錯誤。</span><span class="sxs-lookup"><span data-stu-id="2ff65-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="2ff65-165">`R1(π/2)` 和 `R1(π/4)` 也相當於 `S` 和 `T` 作業 (也在 `Microsoft.Quantum.Intrinsic`) 中。</span><span class="sxs-lookup"><span data-stu-id="2ff65-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="2ff65-166">將相關的 `H` 作業和控制的旋轉套用至第二個和第三個量子位之後：</span><span class="sxs-lookup"><span data-stu-id="2ff65-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="2ff65-167">我們只需要套用一個網 [`SWAP`](xref:Microsoft.Quantum.Intrinsic.SWAP) 關來完成線路：</span><span class="sxs-lookup"><span data-stu-id="2ff65-167">we need only apply a [`SWAP`](xref:Microsoft.Quantum.Intrinsic.SWAP) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="2ff65-168">這是必要的，因為量子傅立葉轉換的本質會以反向順序輸出量子位，因此交換可讓副程式緊密整合到較大的演算法。</span><span class="sxs-lookup"><span data-stu-id="2ff65-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="2ff65-169">因此，我們已完成將量子傅立葉轉換的量子位層級作業寫入我們的作業中 :::no-loc(Q#)::: ：</span><span class="sxs-lookup"><span data-stu-id="2ff65-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our :::no-loc(Q#)::: operation:</span></span>

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="2ff65-170">不過，我們還無法在一天之前呼叫它。</span><span class="sxs-lookup"><span data-stu-id="2ff65-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="2ff65-171">當我們配置量子位時，我們的州/省是 $ \ket {0} $，很像在現實生活中， :::no-loc(Q#)::: 我們應該以與我們一樣的方式，將專案保留 (或更好！ ) 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in :::no-loc(Q#)::: we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="2ff65-172">解除配置量子位</span><span class="sxs-lookup"><span data-stu-id="2ff65-172">Deallocate qubits</span></span>

<span data-ttu-id="2ff65-173">我們 [`DumpMachine()`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) 再次呼叫以查看作業後狀態，最後會套用至量子位暫存器， [`ResetAll`](xref:Microsoft.Quantum.Intrinsic.resetall) 以在完成作業之前將量子位重設為 $ \ket {0} $：</span><span class="sxs-lookup"><span data-stu-id="2ff65-173">We call [`DumpMachine()`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:Microsoft.Quantum.Intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="2ff65-174">要求所有已解除配置的量子位都明確設定為 $ \ket {0} $ 是的基本功能 :::no-loc(Q#)::: ，因為它可讓其他作業在開始使用這些相同的量子位 (稀有資源) 時，精確地知道其狀態。</span><span class="sxs-lookup"><span data-stu-id="2ff65-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of :::no-loc(Q#):::, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="2ff65-175">此外，這可確保它們不會與系統中的任何其他量子位纏結。</span><span class="sxs-lookup"><span data-stu-id="2ff65-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="2ff65-176">如果未在配置區塊的結尾執行重設，則會擲回 `using` 執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="2ff65-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="2ff65-177">您的完整檔案 :::no-loc(Q#)::: 現在看起來應該像這樣：</span><span class="sxs-lookup"><span data-stu-id="2ff65-177">Your full :::no-loc(Q#)::: file should now look like this:</span></span>

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


<span data-ttu-id="2ff65-178">完成檔案 :::no-loc(Q#)::: 和作業之後，就可以呼叫和模擬我們的量副程式。</span><span class="sxs-lookup"><span data-stu-id="2ff65-178">With the :::no-loc(Q#)::: file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="2ff65-179">執行程式</span><span class="sxs-lookup"><span data-stu-id="2ff65-179">Run the program</span></span>

<span data-ttu-id="2ff65-180">在檔案中定義我們的作業之後 :::no-loc(Q#)::: `.qs` ，我們現在需要呼叫該作業，並觀察任何傳回的傳統資料。</span><span class="sxs-lookup"><span data-stu-id="2ff65-180">Having defined our :::no-loc(Q#)::: operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="2ff65-181">目前，沒有任何傳回的 (回想，上述定義的作業會傳回 `Unit`) ，但是當我們稍後修改作業 :::no-loc(Q#)::: 以傳回測量結果陣列 (`Result[]`) 時，我們將會解決此情況。</span><span class="sxs-lookup"><span data-stu-id="2ff65-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the :::no-loc(Q#)::: operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="2ff65-182">雖然 :::no-loc(Q#)::: 程式在用來呼叫它的環境中是普遍的，但這麼做的方式當然會有所不同。</span><span class="sxs-lookup"><span data-stu-id="2ff65-182">While the :::no-loc(Q#)::: program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="2ff65-183">因此，只要依照您的設定所對應的索引標籤中的指示操作：從 :::no-loc(Q#)::: 應用程式或使用 Python 或 c # 中的主機程式來運作。</span><span class="sxs-lookup"><span data-stu-id="2ff65-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the :::no-loc(Q#)::: application or using a host program in Python or C#.</span></span>

#### <a name="command-prompt"></a>[<span data-ttu-id="2ff65-184">命令提示字元</span><span class="sxs-lookup"><span data-stu-id="2ff65-184">Command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="2ff65-185">:::no-loc(Q#):::從命令提示字元執行程式，只需要對檔案進行少許變更 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-185">Running the :::no-loc(Q#)::: program from the command prompt requires only a small change to the :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="2ff65-186">只要新增 `@EntryPoint()` 至作業定義前面的一行即可：</span><span class="sxs-lookup"><span data-stu-id="2ff65-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="2ff65-187">若要執行程式，請在專案的資料夾中開啟終端機，並輸入</span><span class="sxs-lookup"><span data-stu-id="2ff65-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="2ff65-188">完成時，您應該會 `Message` `DumpMachine` 在主控台中看到下列輸出和輸出。</span><span class="sxs-lookup"><span data-stu-id="2ff65-188">Upon completion, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="2ff65-189">Python</span><span class="sxs-lookup"><span data-stu-id="2ff65-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="2ff65-190">建立 Python 主機檔案： `host.py` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="2ff65-191">主機檔案的結構如下：</span><span class="sxs-lookup"><span data-stu-id="2ff65-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="2ff65-192">首先，我們會匯入 `qsharp` 模組，該模組會註冊模組載入器以獲得 :::no-loc(Q#)::: 互通性。</span><span class="sxs-lookup"><span data-stu-id="2ff65-192">First, we import the `qsharp` module, which registers the module loader for :::no-loc(Q#)::: interoperability.</span></span> 
    <span data-ttu-id="2ff65-193">這可讓 :::no-loc(Q#)::: 命名空間 (例如， `NamespaceQFT` 我們在檔案中定義的 :::no-loc(Q#):::) 會顯示為 Python 模組，我們可以從中匯入 :::no-loc(Q#)::: 作業。</span><span class="sxs-lookup"><span data-stu-id="2ff65-193">This allows :::no-loc(Q#)::: namespaces (e.g. the `NamespaceQFT` we defined in our :::no-loc(Q#)::: file) to appear as Python modules, from which we can import :::no-loc(Q#)::: operations.</span></span>
2. <span data-ttu-id="2ff65-194">然後，匯入 :::no-loc(Q#)::: 我們將在此案例中直接叫用---的作業 `Perform3qubitQFT` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-194">Then, import the :::no-loc(Q#)::: operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="2ff65-195">我們只需要將進入點匯入程式中， :::no-loc(Q#)::: (也 _not_ 就是不 `H` 是與等作業 `R1` ，由其他 :::no-loc(Q#)::: 作業呼叫，但傳統主機) 絕不會呼叫。</span><span class="sxs-lookup"><span data-stu-id="2ff65-195">We need only import the entry point into a :::no-loc(Q#)::: program (i.e. _not_ operations like `H` and `R1`, which are called by other :::no-loc(Q#)::: operations but never by the classical host).</span></span>
3. <span data-ttu-id="2ff65-196">在模擬 :::no-loc(Q#)::: 作業或函式時，請使用表單在 `<:::no-loc(Q#):::callable>.simulate(<args>)` `QuantumSimulator()` 目的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="2ff65-196">In simulating :::no-loc(Q#)::: operations or functions, use the form `<:::no-loc(Q#):::callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="2ff65-197">例如，如果我們想要在不同的電腦上呼叫此作業， `ResourceEstimator()` 我們只需要使用 `<:::no-loc(Q#):::callable>.estimate_resources(<args>)` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<:::no-loc(Q#):::callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="2ff65-198">一般情況下， :::no-loc(Q#)::: 作業與執行所在的電腦無關，但某些功能（例如） `DumpMachine` 可能會有不同的行為。</span><span class="sxs-lookup"><span data-stu-id="2ff65-198">In general, :::no-loc(Q#)::: operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="2ff65-199">執行模擬時，操作呼叫會傳回檔案中定義的值 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-199">Upon performing the simulation, the operation call will return values as defined in the :::no-loc(Q#)::: file.</span></span>
    <span data-ttu-id="2ff65-200">現在沒有傳回任何內容，但稍後我們會看到指派和處理這些值的範例。</span><span class="sxs-lookup"><span data-stu-id="2ff65-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="2ff65-201">有了結果的資料，我們就可以用它來做任何想要的結果。</span><span class="sxs-lookup"><span data-stu-id="2ff65-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="2ff65-202">您的完整檔案應如下所 `host.py` 示：</span><span class="sxs-lookup"><span data-stu-id="2ff65-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="2ff65-203">執行 Python 檔案，並列印在主控台中，您應該會看到 `Message` `DumpMachine` 下列輸出。</span><span class="sxs-lookup"><span data-stu-id="2ff65-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="2ff65-204">C#</span><span class="sxs-lookup"><span data-stu-id="2ff65-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="2ff65-205">遵循《 [安裝指南》](xref:microsoft.quantum.install.cs)中的相同指示，建立 c # 主機檔案，然後將它重新命名為 `host.cs` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="2ff65-206">C # 主機有四個部分：</span><span class="sxs-lookup"><span data-stu-id="2ff65-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="2ff65-207">建構量子模擬器。</span><span class="sxs-lookup"><span data-stu-id="2ff65-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="2ff65-208">在下列程式碼中，這是變數 `qsim` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="2ff65-209">計算量子演算法所需的任何引數。</span><span class="sxs-lookup"><span data-stu-id="2ff65-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="2ff65-210">此範例中沒有任何內容。</span><span class="sxs-lookup"><span data-stu-id="2ff65-210">There are none in this example.</span></span>
3. <span data-ttu-id="2ff65-211">執行量子演算法。</span><span class="sxs-lookup"><span data-stu-id="2ff65-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="2ff65-212">每個作業 :::no-loc(Q#)::: 都會產生具有相同名稱的 c # 類別。</span><span class="sxs-lookup"><span data-stu-id="2ff65-212">Each :::no-loc(Q#)::: operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="2ff65-213">此類別的 `Run` 方法會以 **非同步方式** 執行作業。</span><span class="sxs-lookup"><span data-stu-id="2ff65-213">This class has a `Run` method that runs the operation **asynchronously** .</span></span>
    <span data-ttu-id="2ff65-214">執行是非同步，因為在實際的硬體上執行它將會是非同步。</span><span class="sxs-lookup"><span data-stu-id="2ff65-214">The run is asynchronous because running it on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="2ff65-215">因為此 `Run` 方法是非同步，所以我們會呼叫 `Wait()` 方法; 這會封鎖執行，直到工作完成並以同步方式傳回結果為止。</span><span class="sxs-lookup"><span data-stu-id="2ff65-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks the run until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="2ff65-216">處理傳回的作業結果。</span><span class="sxs-lookup"><span data-stu-id="2ff65-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="2ff65-217">目前，作業不會傳回任何內容。</span><span class="sxs-lookup"><span data-stu-id="2ff65-217">For now, the operation returns nothing.</span></span>


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
<span data-ttu-id="2ff65-218">執行應用程式，您的輸出應該會符合下面的結果。</span><span class="sxs-lookup"><span data-stu-id="2ff65-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="2ff65-219">當您按下按鍵後，程式就會結束。</span><span class="sxs-lookup"><span data-stu-id="2ff65-219">The program will exit after you press a key.</span></span>
<span data-ttu-id="2ff65-220">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2ff65-220">\*\*_</span></span>

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     _******************* [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     **_                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
```

<span data-ttu-id="2ff65-221">在完整狀態模擬器上呼叫時，會 `DumpMachine()` 提供這些量子狀態 wavefunction 的多重標記法。</span><span class="sxs-lookup"><span data-stu-id="2ff65-221">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="2ff65-222">$N $-量子位系統的可能狀態可以用 $ 2 ^ n $ 計算基礎狀態表示，每一個都有相對應的複數 (只是一個振幅和一個階段) 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-222">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="2ff65-223">計算基礎狀態會對應至長度 $n $---的所有可能二進位字串，也就是量子位狀態 $ \ket {0} $ 和 $ \ket $ 的所有可能組合 {1} ，其中每個二進位數都對應到個別量子位。</span><span class="sxs-lookup"><span data-stu-id="2ff65-223">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="2ff65-224">第一個資料列會以其重大順序提供批註，內含對應量子位的識別碼。</span><span class="sxs-lookup"><span data-stu-id="2ff65-224">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="2ff65-225">量子位是「 `2` 最重要的」，只是表示在基礎狀態向量 $ \ket{i} $ 的二進位標記法中，量子位的狀態 `2` 對應到最左邊的數位。</span><span class="sxs-lookup"><span data-stu-id="2ff65-225">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="2ff65-226">例如，$ \ket {6} = \ket {110} $ 的組成量子位 `2` ，以及 $ `1` \ket {1} $ 和量子位 `0` in $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="2ff65-226">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="2ff65-227">其餘的資料列描述測量以笛卡兒和極座標形式測量基礎狀態向量 $ \ket{i} $ 的機率幅度。</span><span class="sxs-lookup"><span data-stu-id="2ff65-227">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="2ff65-228">針對輸入狀態 $ \ket $： _ 的第一個資料列， {000} **`|0>:`** 這個資料列會對應至 `0` 計算基礎狀態， (假設我們的初始狀態後置配置為 $ \ket {000} $，我們預期這是具有機率幅度的唯一狀態) 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-228">In detail for the first row of our input state $\ket{000}$: _ **`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="2ff65-229">**`1.000000 +  0.000000 i`** ：笛卡兒格式的機率幅度。</span><span class="sxs-lookup"><span data-stu-id="2ff65-229">**`1.000000 +  0.000000 i`** : the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="2ff65-230">**` == `** ： `equal` 符號會分隔兩個對等的表示。</span><span class="sxs-lookup"><span data-stu-id="2ff65-230">**` == `** : the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="2ff65-231">**`********************`** ：量值的圖形表示，的數目 `*` 會與測量這個狀態向量的機率成正比。</span><span class="sxs-lookup"><span data-stu-id="2ff65-231">**`********************`** : A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="2ff65-232">**`[ 1.000000 ]`** ：量值的數值</span><span class="sxs-lookup"><span data-stu-id="2ff65-232">**`[ 1.000000 ]`** : the numeric value of the magnitude</span></span>
* <span data-ttu-id="2ff65-233">**`    ---`** ：振幅階段的圖形表示。</span><span class="sxs-lookup"><span data-stu-id="2ff65-233">**`    ---`** : A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="2ff65-234">**`[ 0.0000 rad ]`** ：階段的數值 (弧度) 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-234">**`[ 0.0000 rad ]`** : the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="2ff65-235">大小和階段都會以圖形表示顯示。</span><span class="sxs-lookup"><span data-stu-id="2ff65-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="2ff65-236">量值的表示方式很簡單：它會顯示一個橫條 `*` ，而機率愈高，則會顯示較大的橫條。</span><span class="sxs-lookup"><span data-stu-id="2ff65-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="2ff65-237">針對階段，請參閱 [測試和偵測：](xref:microsoft.quantum.guide.testingdebugging#dump-functions) 根據角度範圍的可能符號表示傾印函數。</span><span class="sxs-lookup"><span data-stu-id="2ff65-237">For the phase, see [Testing and debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="2ff65-238">因此，列印的輸出會說明我們的程式設計閘道將我們的狀態轉換為</span><span class="sxs-lookup"><span data-stu-id="2ff65-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="2ff65-239">$ $ \ket{\psi} \_ {初始} = \ket {000} $ $</span><span class="sxs-lookup"><span data-stu-id="2ff65-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="2ff65-240">to</span><span class="sxs-lookup"><span data-stu-id="2ff65-240">to</span></span> 

<span data-ttu-id="2ff65-241">$ $ \begin{align} \ket{\psi} \_ {final} &= \frac {1} {\sqrt {8} } \left ( \ket {000} + \ket {001} + \ket + \ket {010} {011} + \ket {100} + \ket {101} + \ket + \ket {110} {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}，\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="2ff65-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="2ff65-242">這是量子位傅立葉轉換的精確行為。</span><span class="sxs-lookup"><span data-stu-id="2ff65-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="2ff65-243">如果您對其他輸入狀態的影響有好奇，建議您在轉換之前，先套用量子位作業。</span><span class="sxs-lookup"><span data-stu-id="2ff65-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="2ff65-244">新增度量</span><span class="sxs-lookup"><span data-stu-id="2ff65-244">Adding measurements</span></span>

<span data-ttu-id="2ff65-245">可惜的是，量子機制的基石告訴我們，真正的量子系統不能有這類 `DumpMachine` 功能。</span><span class="sxs-lookup"><span data-stu-id="2ff65-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="2ff65-246">相反地，我們會強制透過度量來解壓縮資訊，而這通常不僅無法提供我們完整的量子狀態，還能大幅改變系統本身。</span><span class="sxs-lookup"><span data-stu-id="2ff65-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="2ff65-247">量子測量有許多種，但我們會將焦點放在單一量子位上最基本的： projective 測量。</span><span class="sxs-lookup"><span data-stu-id="2ff65-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="2ff65-248">以給定的度量進行測量時 (例如，計算基礎 $ \{ \ket {0} 、\ket {1} \} $) 、量子位狀態會投射到任何測量的基礎狀態---因此會終結兩者之間的任何迭加。</span><span class="sxs-lookup"><span data-stu-id="2ff65-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="2ff65-249">為了在程式內執行度量 :::no-loc(Q#)::: ，我們會使用 `M` 從) 傳回類型的作業 (`Microsoft.Quantum.Intrinsic` `Result` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-249">To implement measurements within a :::no-loc(Q#)::: program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="2ff65-250">首先，我們會修改作業 `Perform3QubitQFT` 來傳回測量結果的陣列， `Result[]` 而不是 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="2ff65-251">定義和初始化 `Result[]` 陣列</span><span class="sxs-lookup"><span data-stu-id="2ff65-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="2ff65-252">在甚至是配置量子位之前 (也就是在 `using` 語句) 之前，我們會宣告並系結此長度3陣列 (`Result` 每個量子位) 各一個：</span><span class="sxs-lookup"><span data-stu-id="2ff65-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="2ff65-253">`mutable`關鍵字接下來 `resultArray` 允許稍後在程式碼中重新綁定變數---例如，在新增測量結果時。</span><span class="sxs-lookup"><span data-stu-id="2ff65-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="2ff65-254">在迴圈中執行測量 `for` ，並將結果新增至陣列</span><span class="sxs-lookup"><span data-stu-id="2ff65-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="2ff65-255">在區塊內的傅立葉轉換作業之後 `using` ，插入下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="2ff65-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="2ff65-256">[`IndexRange`](xref:Microsoft.Quantum.Arrays.IndexRange)在陣列上呼叫的函式 (例如我們量子位的陣列， `qs`) 傳回陣列索引的範圍。</span><span class="sxs-lookup"><span data-stu-id="2ff65-256">The [`IndexRange`](xref:Microsoft.Quantum.Arrays.IndexRange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="2ff65-257">在這裡，我們會在迴圈中使用它， `for` 以依序使用語句來測量每個量子位 `M(qs[i])` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="2ff65-258">每個測量的 `Result` 類型 (`Zero` 或 `One`) 接著會 `resultArray` 使用 update 和重新指派語句新增至中的對應索引位置。</span><span class="sxs-lookup"><span data-stu-id="2ff65-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="2ff65-259">這個語句的語法對而言是唯一的 :::no-loc(Q#)::: ，但是會對應到 `resultArray[i] <- M(qs[i])` 其他語言（例如 F # 和 R）中所看到的類似變數重新指派。</span><span class="sxs-lookup"><span data-stu-id="2ff65-259">The syntax of this statement is unique to :::no-loc(Q#):::, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="2ff65-260">關鍵字 `set` 一律用來重新指派使用系結的變數 `mutable` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="2ff65-261">返回 `resultArray`</span><span class="sxs-lookup"><span data-stu-id="2ff65-261">Return `resultArray`</span></span>

<span data-ttu-id="2ff65-262">所有三個量子位都經過測量，並將結果加入至 `resultArray` 之後，我們就可以安全地重設和解除配置量子位。</span><span class="sxs-lookup"><span data-stu-id="2ff65-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="2ff65-263">在 `using` 區塊關閉之後，插入</span><span class="sxs-lookup"><span data-stu-id="2ff65-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="2ff65-264">最後會傳回作業的輸出。</span><span class="sxs-lookup"><span data-stu-id="2ff65-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="2ff65-265">瞭解測量的影響</span><span class="sxs-lookup"><span data-stu-id="2ff65-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="2ff65-266">讓我們變更函式的位置， `DumpMachine` 以輸出度量前後的狀態。</span><span class="sxs-lookup"><span data-stu-id="2ff65-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="2ff65-267">最終的作業程式碼看起來應該像這樣：</span><span class="sxs-lookup"><span data-stu-id="2ff65-267">The final operation code should look like:</span></span> 

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

<span data-ttu-id="2ff65-268">如果您是從命令提示字元工作，傳回的陣列只會在執行結束時直接顯示在主控台中。</span><span class="sxs-lookup"><span data-stu-id="2ff65-268">If you are working from the command prompt, the returned array will simply be displayed directly to the console at the end of the run.</span></span>
<span data-ttu-id="2ff65-269">否則，請更新您的主機程式以處理傳回的陣列。</span><span class="sxs-lookup"><span data-stu-id="2ff65-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-prompt"></a>[<span data-ttu-id="2ff65-270">命令提示字元</span><span class="sxs-lookup"><span data-stu-id="2ff65-270">Command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="2ff65-271">若要更瞭解將在主控台中列印的傳回陣列，我們可以 `Message` 在語句之前的檔案中加入另一個 :::no-loc(Q#)::: `return` ：</span><span class="sxs-lookup"><span data-stu-id="2ff65-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the :::no-loc(Q#)::: file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="2ff65-272">執行專案，您的輸出看起來應該會如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ff65-272">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     **_                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     _******************* [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[<span data-ttu-id="2ff65-273">Python</span><span class="sxs-lookup"><span data-stu-id="2ff65-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="2ff65-274">將您的 Python 程式更新為下列內容：</span><span class="sxs-lookup"><span data-stu-id="2ff65-274">Update your Python program to the following:</span></span>

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

<span data-ttu-id="2ff65-275">執行檔案，您的輸出看起來應該會如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ff65-275">Run the file, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     **_                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     _******************* [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[<span data-ttu-id="2ff65-276">C#</span><span class="sxs-lookup"><span data-stu-id="2ff65-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="2ff65-277">現在，我們的作業會傳回結果，請 `Wait()` 以提取屬性取代方法呼叫 `Result` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="2ff65-278">這仍會完成先前討論過的相同同步性，我們可以直接將此值系結至變數 `measurementResult` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

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

<span data-ttu-id="2ff65-279">執行專案，您的輸出看起來應該會如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ff65-279">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     **_                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     _*_                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     _******************* [ 1.000000 ]     --- [  0.00000 rad ]
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

<span data-ttu-id="2ff65-280">此輸出說明一些不同的專案：</span><span class="sxs-lookup"><span data-stu-id="2ff65-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="2ff65-281">將傳回的結果與預先度量比較 `DumpMachine` ，顯然不會說明 _not_ QFT 後迭加的基礎狀態。</span><span class="sxs-lookup"><span data-stu-id="2ff65-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="2ff65-282">度量只會傳回單一基礎狀態，並在系統 wavefunction 中以該狀態的波幅決定機率。</span><span class="sxs-lookup"><span data-stu-id="2ff65-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="2ff65-283">從之後的測量結果 `DumpMachine` ，我們發現測量 _改變_ 了狀態本身，將其從初始迭加的基礎狀態投射到對應至測量值的單一基礎狀態。</span><span class="sxs-lookup"><span data-stu-id="2ff65-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="2ff65-284">如果我們要重複執行這項作業多次，我們會看到結果統計資料開始說明 QFT 後狀態的平均加權迭加，這會導致每個快照的隨機結果。</span><span class="sxs-lookup"><span data-stu-id="2ff65-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="2ff65-285">_但是_ ，除了效率不佳且仍然完美之外，這只會重現基礎狀態的相對 amplitudes，而不是兩者之間的相對階段。</span><span class="sxs-lookup"><span data-stu-id="2ff65-285">_However_ , besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="2ff65-286">後者在此範例中並不是問題，但如果提供比 $ \ket $ 更複雜的 QFT 輸入，則會看到相對階段。 {000}</span><span class="sxs-lookup"><span data-stu-id="2ff65-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="2ff65-287">部分度量</span><span class="sxs-lookup"><span data-stu-id="2ff65-287">Partial measurements</span></span> 
<span data-ttu-id="2ff65-288">若要探索如何只測量註冊的部分量子位可能會影響系統的狀態，請嘗試在 `for` 測量線之後，于迴圈內新增下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="2ff65-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="2ff65-289">請注意，若要存取函式， `IntAsString` 您將必須新增</span><span class="sxs-lookup"><span data-stu-id="2ff65-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="2ff65-290">以及命名空間語句的其餘部分 `open` 。</span><span class="sxs-lookup"><span data-stu-id="2ff65-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="2ff65-291">在產生的輸出中，您會在測量每個量子位時看到逐步投射至 subspaces。</span><span class="sxs-lookup"><span data-stu-id="2ff65-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-no-locq-libraries"></a><span data-ttu-id="2ff65-292">使用連結 :::no-loc(Q#)::: 庫</span><span class="sxs-lookup"><span data-stu-id="2ff65-292">Use the :::no-loc(Q#)::: libraries</span></span>
<span data-ttu-id="2ff65-293">如同我們在簡介中所述，大部分的 :::no-loc(Q#)::: 功能都能讓您抽象化處理個別的量子位。</span><span class="sxs-lookup"><span data-stu-id="2ff65-293">As we mentioned in the introduction, much of :::no-loc(Q#):::'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="2ff65-294">事實上，如果您想要開發全方位、適用的量副程式，請擔心某項作業 `H` 在特定輪替之前或之後是否會變慢。</span><span class="sxs-lookup"><span data-stu-id="2ff65-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="2ff65-295">連結 :::no-loc(Q#)::: 庫包含 [QFT](xref:Microsoft.Quantum.Canon.QFT) 作業，您可以直接採用並套用至任意數目的量子位。</span><span class="sxs-lookup"><span data-stu-id="2ff65-295">The :::no-loc(Q#)::: libraries contain the [QFT](xref:Microsoft.Quantum.Canon.QFT) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="2ff65-296">若要試試看，請在您的檔案中定義 :::no-loc(Q#)::: 具有相同內容的新作業 `Perform3QubitQFT` ，但是從第一個的所有專案，都是 `H` `SWAP` 由兩個簡單的程式碼所取代：</span><span class="sxs-lookup"><span data-stu-id="2ff65-296">To give it a try, define a new operation in your :::no-loc(Q#)::: file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="2ff65-297">第一行只 [`BigEndian`](xref:Microsoft.Quantum.Arithmetic.BigEndian) 會建立已配置量子位陣列的運算式， `qs` 這是 [QFT](xref:Microsoft.Quantum.Canon.QFT) 作業做為引數所採用的運算式。</span><span class="sxs-lookup"><span data-stu-id="2ff65-297">The first line simply creates a [`BigEndian`](xref:Microsoft.Quantum.Arithmetic.BigEndian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:Microsoft.Quantum.Canon.QFT) operation takes as an argument.</span></span>
<span data-ttu-id="2ff65-298">這對應于註冊中量子位的索引順序。</span><span class="sxs-lookup"><span data-stu-id="2ff65-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="2ff65-299">若要存取這些作業，請 `open` 在檔案的開頭新增其各自命名空間的語句 :::no-loc(Q#)::: ：</span><span class="sxs-lookup"><span data-stu-id="2ff65-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the :::no-loc(Q#)::: file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="2ff65-300">現在，調整您的主機程式以呼叫新作業的名稱 (例如 `PerformIntrinsicQFT`) ，並為其提供 whirl。</span><span class="sxs-lookup"><span data-stu-id="2ff65-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="2ff65-301">若要瞭解使用程式庫作業的真正優點 :::no-loc(Q#)::: ，請將量子位數目變更為以下以外的值 `3` ：</span><span class="sxs-lookup"><span data-stu-id="2ff65-301">To see the real benefit of using the :::no-loc(Q#)::: library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4];

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="2ff65-302">因此，您可以針對任何指定的量子位數目套用適當的 QFT，而不需要擔心 `H` 每個量子位的新作業和旋轉。</span><span class="sxs-lookup"><span data-stu-id="2ff65-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="2ff65-303">請注意，當您增加量子位數目時，量子模擬器會以指數方式執行一次以上的時間，---精確地查看真正的量子硬體！</span><span class="sxs-lookup"><span data-stu-id="2ff65-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>
