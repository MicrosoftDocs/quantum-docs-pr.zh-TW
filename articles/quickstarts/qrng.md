---
title: 建立量子亂數產生器
description: 建置一個 Q# 專案，透過建立量子亂數產生器來示範基本的量子概念，例如疊加。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 8fafbccfe2a94a824353221b5e7eb8bac16c42f2
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327351"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="b9d12-103">教學課程：在 Q\# 中實作量子亂數產生器</span><span class="sxs-lookup"><span data-stu-id="b9d12-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="b9d12-104">量子亂數產生器是以 Q # 撰寫量子演算法的一個簡單範例。</span><span class="sxs-lookup"><span data-stu-id="b9d12-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="b9d12-105">此演算法利用量子機制的本質來產生亂數。</span><span class="sxs-lookup"><span data-stu-id="b9d12-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b9d12-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="b9d12-106">Prerequisites</span></span>

- <span data-ttu-id="b9d12-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="b9d12-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="b9d12-108">[從命令列使用 Q#](xref:microsoft.quantum.install.standalone)，或使用 [Python 主機程式](xref:microsoft.quantum.install.python) 或 [C# 主機程式](xref:microsoft.quantum.install.cs)，建立 Q# 專案。</span><span class="sxs-lookup"><span data-stu-id="b9d12-108">Create a Q# project for either [using Q# from the command line](xref:microsoft.quantum.install.standalone), or with a [Python host program](xref:microsoft.quantum.install.python) or [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="write-a-q-operation"></a><span data-ttu-id="b9d12-109">撰寫 Q# 作業</span><span class="sxs-lookup"><span data-stu-id="b9d12-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="b9d12-110">Q# 作業程式碼</span><span class="sxs-lookup"><span data-stu-id="b9d12-110">Q# operation code</span></span>

1. <span data-ttu-id="b9d12-111">使用下列程式碼取代 Program.qs 檔案的內容：</span><span class="sxs-lookup"><span data-stu-id="b9d12-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="b9d12-112">如[了解量子運算](xref:microsoft.quantum.overview.understanding)一文所述，量子位元是一種可疊加的量子資訊單位。</span><span class="sxs-lookup"><span data-stu-id="b9d12-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="b9d12-113">測量時，量子位元只能是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="b9d12-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="b9d12-114">不過在執行期間，量子位元的狀態代表著測量讀數為 0 或 1 的機率。</span><span class="sxs-lookup"><span data-stu-id="b9d12-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="b9d12-115">這個概率性的狀態稱為疊加。</span><span class="sxs-lookup"><span data-stu-id="b9d12-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="b9d12-116">我們可以使用此機率來產生亂數。</span><span class="sxs-lookup"><span data-stu-id="b9d12-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="b9d12-117">在我們的 Q# 作業中，我們引進 Q# 原生的 `Qubit` 資料類型。</span><span class="sxs-lookup"><span data-stu-id="b9d12-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="b9d12-118">我們只能使用 `using` 陳述式來配置 `Qubit`。</span><span class="sxs-lookup"><span data-stu-id="b9d12-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="b9d12-119">當量子位元獲得配置時，一定會處於 `Zero` 狀態。</span><span class="sxs-lookup"><span data-stu-id="b9d12-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="b9d12-120">使用 `H` 作業，我們可以將 `Qubit` 置於疊加狀態。</span><span class="sxs-lookup"><span data-stu-id="b9d12-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="b9d12-121">若要測量量子位元並讀取其值，請使用 `M` 內建作業。</span><span class="sxs-lookup"><span data-stu-id="b9d12-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="b9d12-122">藉由將 `Qubit` 置於疊加並加以測量，每次叫用程式碼時，結果就會是不同的值。</span><span class="sxs-lookup"><span data-stu-id="b9d12-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="b9d12-123">解除配置 `Qubit` 時，必須將它明確設定回 `Zero` 狀態，否則模擬器將會報告執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="b9d12-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="b9d12-124">叫用 `Reset` 是達成此動作的簡單做法。</span><span class="sxs-lookup"><span data-stu-id="b9d12-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="b9d12-125">使用布洛赫球體將程式碼視覺化</span><span class="sxs-lookup"><span data-stu-id="b9d12-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="b9d12-126">在布洛赫球體中，北極點代表古典值 **0**，而南極點代表古典值 **1**。</span><span class="sxs-lookup"><span data-stu-id="b9d12-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="b9d12-127">任何疊加都可以用球體上的點表示 (以箭頭表示)。</span><span class="sxs-lookup"><span data-stu-id="b9d12-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="b9d12-128">箭頭末端愈接近極點時，量子位元在測量時塌縮為指派給該極點的古典值的機率愈高。</span><span class="sxs-lookup"><span data-stu-id="b9d12-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="b9d12-129">例如，下面紅色箭頭所表示的量子位元 狀態，在我們測量它時有較高的機率是 **0** 值。</span><span class="sxs-lookup"><span data-stu-id="b9d12-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="b9d12-130">我們可以用這個表示方式來將程式碼的作用視覺化呈現：</span><span class="sxs-lookup"><span data-stu-id="b9d12-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="b9d12-131">首先，我們讓量子位元的初始狀態為 **0**，並套用 `H` 來建立疊加，疊加的 **0** 和 **1** 機率相同。</span><span class="sxs-lookup"><span data-stu-id="b9d12-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="b9d12-132">然後，我們測量量子位元並儲存輸出：</span><span class="sxs-lookup"><span data-stu-id="b9d12-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="b9d12-133">由於測量的結果完全隨機，我們便能得到一個隨機位元。</span><span class="sxs-lookup"><span data-stu-id="b9d12-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="b9d12-134">我們可以呼叫此作業多次來建立整數。</span><span class="sxs-lookup"><span data-stu-id="b9d12-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="b9d12-135">例如，如果我們呼叫此作業三次來取得三個隨機位元，則可以建立隨機的 3位元數字 (也就是介於 0 和 7 之間的亂數)。</span><span class="sxs-lookup"><span data-stu-id="b9d12-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="b9d12-136">建立完整的亂數產生器</span><span class="sxs-lookup"><span data-stu-id="b9d12-136">Creating a complete random number generator</span></span>

<span data-ttu-id="b9d12-137">既然我們已經有產生隨機位元的 Q # 作業，我們可以用來建立完整的量子亂數產生器。</span><span class="sxs-lookup"><span data-stu-id="b9d12-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="b9d12-138">我們可以使用 Q # 命令列應用程式或使用主機程式。</span><span class="sxs-lookup"><span data-stu-id="b9d12-138">We can use the Q# command line applications or use a host program.</span></span>



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="b9d12-139">具有 Visual Studio 或 Visual Studio Code 的 Q # 命令列應用程式</span><span class="sxs-lookup"><span data-stu-id="b9d12-139">Q# command line applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="b9d12-140">若要建立完整的 Q # 命令列應用程式，請將下列進入點新增至您的 Q # 程式：</span><span class="sxs-lookup"><span data-stu-id="b9d12-140">To create the full Q# command line application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="b9d12-141">視專案設定和命令列選項而定，可執行檔將會在模擬器或資源估計工具上執行標記為 `@EntryPoint()` 屬性的作業或函式。</span><span class="sxs-lookup"><span data-stu-id="b9d12-141">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="b9d12-142">在 Visual Studio 中，只要按 Ctrl + F5 執行指令碼即可。</span><span class="sxs-lookup"><span data-stu-id="b9d12-142">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="b9d12-143">在 VS Code 中，透過在終端機中輸入下列命令，以第一次建立 Program.qs：</span><span class="sxs-lookup"><span data-stu-id="b9d12-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="b9d12-144">在後續的執行中，不需要重新建立。</span><span class="sxs-lookup"><span data-stu-id="b9d12-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="b9d12-145">若要執行，請輸入下列命令並按 Enter 鍵：</span><span class="sxs-lookup"><span data-stu-id="b9d12-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="b9d12-146">使用 Visual Studio Code 或命令列的 Python</span><span class="sxs-lookup"><span data-stu-id="b9d12-146">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

<span data-ttu-id="b9d12-147">若要從 Python 執行新的 Q# 程式，請將下列程式碼儲存為 `host.py`：</span><span class="sxs-lookup"><span data-stu-id="b9d12-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="b9d12-148">然後，您可以從命令列執行 Python 主機程式：</span><span class="sxs-lookup"><span data-stu-id="b9d12-148">You can then run your Python host program from the command line:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="b9d12-149">擁有 Visual Studio Code 或 Visual Studio 的 C#</span><span class="sxs-lookup"><span data-stu-id="b9d12-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="b9d12-150">若要從 C# 執行新的 Q# 程式，請修改 `Driver.cs` 以納入下列 C# 程式碼：</span><span class="sxs-lookup"><span data-stu-id="b9d12-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="b9d12-151">然後，您可以從命令列 (在 Visual Studio 中您必須按 F5) 執行 C# 主機程式：</span><span class="sxs-lookup"><span data-stu-id="b9d12-151">You can then run your C# host program from the command line (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
