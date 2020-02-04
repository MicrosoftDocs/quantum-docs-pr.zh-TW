---
title: 建立量子亂數產生器
description: 建置一個 Q# 專案，透過建立量子亂數產生器來示範基本的量子概念，例如疊加。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 134617455b720cc755b9ee9fb68fb59e624d3f1a
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820896"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="f3efe-103">快速入門：在 Q# 中實作量子亂數產生器</span><span class="sxs-lookup"><span data-stu-id="f3efe-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="f3efe-104">量子亂數產生器是以 Q # 撰寫量子演算法的一個簡單範例。</span><span class="sxs-lookup"><span data-stu-id="f3efe-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="f3efe-105">此演算法利用量子機制的本質來產生亂數。</span><span class="sxs-lookup"><span data-stu-id="f3efe-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f3efe-106">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="f3efe-106">Prerequisites</span></span>

- <span data-ttu-id="f3efe-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="f3efe-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="f3efe-108">建立 Q# 專案</span><span class="sxs-lookup"><span data-stu-id="f3efe-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="f3efe-109">撰寫 Q# 作業</span><span class="sxs-lookup"><span data-stu-id="f3efe-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="f3efe-110">Q# 作業程式碼</span><span class="sxs-lookup"><span data-stu-id="f3efe-110">Q# operation code</span></span>

1. <span data-ttu-id="f3efe-111">以下列程式碼取代 Operation.qs 檔案的內容：</span><span class="sxs-lookup"><span data-stu-id="f3efe-111">Replace the contents of the Operation.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(qubit = Qubit())  { // Allocate a qubit.
                H(qubit);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(v);     // Measure the qubit value.
                Reset(qubit);
                return r;
            }
        }
    }
    ```

<span data-ttu-id="f3efe-112">如[什麼是量子運算？](xref:microsoft.quantum.overview.what)文中所述，量子位元是一種可疊加的量子資訊單位。</span><span class="sxs-lookup"><span data-stu-id="f3efe-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="f3efe-113">測量時，量子位元只能是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="f3efe-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="f3efe-114">不過在執行期間，量子位元的狀態代表著測量讀數為 0 或 1 的機率。</span><span class="sxs-lookup"><span data-stu-id="f3efe-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="f3efe-115">這個概率性的狀態稱為疊加。</span><span class="sxs-lookup"><span data-stu-id="f3efe-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="f3efe-116">我們可以使用此機率來產生亂數。</span><span class="sxs-lookup"><span data-stu-id="f3efe-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="f3efe-117">在我們的 Q# 作業中，我們引進 Q# 原生的 `Qubit` 資料類型。</span><span class="sxs-lookup"><span data-stu-id="f3efe-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="f3efe-118">我們只能使用 `using` 陳述式來配置 `Qubit`。</span><span class="sxs-lookup"><span data-stu-id="f3efe-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="f3efe-119">當量子位元獲得配置時，一定會處於 `Zero` 狀態。</span><span class="sxs-lookup"><span data-stu-id="f3efe-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="f3efe-120">使用 `H` 作業，我們可以將 `Qubit` 置於疊加狀態。</span><span class="sxs-lookup"><span data-stu-id="f3efe-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="f3efe-121">若要測量量子位元並讀取其值，請使用 `M` 內建作業。</span><span class="sxs-lookup"><span data-stu-id="f3efe-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="f3efe-122">藉由將 `Qubit` 置於疊加並加以測量，每次叫用程式碼時，結果就會是不同的值。</span><span class="sxs-lookup"><span data-stu-id="f3efe-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="f3efe-123">解除配置 `Qubit` 時，必須將它明確設定回 `Zero` 狀態，否則模擬器將會報告執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="f3efe-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="f3efe-124">叫用 `Reset` 是達成此動作的簡單做法。</span><span class="sxs-lookup"><span data-stu-id="f3efe-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="f3efe-125">使用布洛赫球體將程式碼視覺化</span><span class="sxs-lookup"><span data-stu-id="f3efe-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="f3efe-126">在布洛赫球體中，北極點代表古典值 **0**，而南極點代表古典值 **1**。</span><span class="sxs-lookup"><span data-stu-id="f3efe-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="f3efe-127">任何疊加都可以用球體上的點表示 (以箭頭表示)。</span><span class="sxs-lookup"><span data-stu-id="f3efe-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="f3efe-128">箭頭末端愈接近極點時，量子位元在測量時塌縮為指派給該極點的古典值的機率愈高。</span><span class="sxs-lookup"><span data-stu-id="f3efe-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="f3efe-129">例如，下面紅色箭頭所表示的量子位元 狀態，在我們測量它時有較高的機率是 **0** 值。</span><span class="sxs-lookup"><span data-stu-id="f3efe-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175">

<span data-ttu-id="f3efe-130">我們可以用這個表示方式來將程式碼的作用視覺化呈現：</span><span class="sxs-lookup"><span data-stu-id="f3efe-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="f3efe-131">首先，我們讓量子位元的初始狀態為 **0**，並套用 `H` 來建立疊加，疊加的 **0** 和 **1** 機率相同。</span><span class="sxs-lookup"><span data-stu-id="f3efe-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450">

* <span data-ttu-id="f3efe-132">然後，我們測量量子位元並儲存輸出：</span><span class="sxs-lookup"><span data-stu-id="f3efe-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450">

<span data-ttu-id="f3efe-133">由於測量的結果完全隨機，我們便能得到一個隨機位元。</span><span class="sxs-lookup"><span data-stu-id="f3efe-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="f3efe-134">我們可以呼叫此作業多次來建立整數。</span><span class="sxs-lookup"><span data-stu-id="f3efe-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="f3efe-135">例如，如果我們呼叫此作業三次來取得三個隨機位元，則可以建立隨機的 3位元數字 (也就是介於 0 和 7 之間的亂數)。</span><span class="sxs-lookup"><span data-stu-id="f3efe-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a><span data-ttu-id="f3efe-136">使用主機程式建立完整的亂數產生器</span><span class="sxs-lookup"><span data-stu-id="f3efe-136">Creating a complete random number generator using a host program</span></span>

<span data-ttu-id="f3efe-137">既然我們已經有產生隨機位的 Q # 作業，我們可以用來建立完整的配量亂數產生器與主機程式。</span><span class="sxs-lookup"><span data-stu-id="f3efe-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator with a host program.</span></span>

 ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="f3efe-138">使用 Visual Studio Code 或命令列的 Python</span><span class="sxs-lookup"><span data-stu-id="f3efe-138">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)
 
 <span data-ttu-id="f3efe-139">若要從 Python 執行新的 Q# 程式，請將下列程式碼儲存為 `host.py`：</span><span class="sxs-lookup"><span data-stu-id="f3efe-139">To run your new Q# program from Python, save the following code as `host.py`:</span></span>
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 <span data-ttu-id="f3efe-140">然後，您可以從命令列執行 Python 主機程式：</span><span class="sxs-lookup"><span data-stu-id="f3efe-140">You can then run your Python host program from the command line:</span></span>
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="f3efe-141">使用 Visual Studio Code 或命令列的 C#</span><span class="sxs-lookup"><span data-stu-id="f3efe-141">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)
 
 <span data-ttu-id="f3efe-142">若要從 C# 執行新的 Q# 程式，請修改 `Driver.cs` 以納入下列 C# 程式碼：</span><span class="sxs-lookup"><span data-stu-id="f3efe-142">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 <span data-ttu-id="f3efe-143">然後，您可以從命令列執行 C# 主機程式：</span><span class="sxs-lookup"><span data-stu-id="f3efe-143">You can then run your C# host program from the command line:</span></span>
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="f3efe-144">使用 Visual Studio 2019 的 C#</span><span class="sxs-lookup"><span data-stu-id="f3efe-144">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

 <span data-ttu-id="f3efe-145">若要從 Visual Studio 中的 C# 執行新的 Q# 程式，請修改 `Driver.cs` 以納入下列 C# 程式碼：</span><span class="sxs-lookup"><span data-stu-id="f3efe-145">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 <span data-ttu-id="f3efe-146">然後按 F5 鍵，程式會開始執行，並跳出一個新視窗顯示產生的亂數：</span><span class="sxs-lookup"><span data-stu-id="f3efe-146">Then press F5, the program will start execution and a new window will pop up with the random number generated:</span></span> 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
