---
title: 建立量子亂數產生器
description: 建置一個 Q# 專案，透過建立量子亂數產生器來示範基本的量子概念，例如疊加。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: a7c077eda3e46430cbe6598cb899adb460451f75
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443914"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="24461-103">快速入門：在 Q# 中實作量子亂數產生器</span><span class="sxs-lookup"><span data-stu-id="24461-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="24461-104">量子亂數產生器是以 Q # 撰寫量子演算法的一個簡單範例。</span><span class="sxs-lookup"><span data-stu-id="24461-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="24461-105">此演算法利用量子機制的本質來產生亂數。</span><span class="sxs-lookup"><span data-stu-id="24461-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="24461-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="24461-106">Prerequisites</span></span>

- <span data-ttu-id="24461-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="24461-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="24461-108">建立 Q# 專案</span><span class="sxs-lookup"><span data-stu-id="24461-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="24461-109">撰寫 Q# 作業</span><span class="sxs-lookup"><span data-stu-id="24461-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="24461-110">Q# 作業程式碼</span><span class="sxs-lookup"><span data-stu-id="24461-110">Q# operation code</span></span>

1. <span data-ttu-id="24461-111">以下列程式碼取代 Operation.qs 檔案的內容：</span><span class="sxs-lookup"><span data-stu-id="24461-111">Replace the contents of the Operation.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

<span data-ttu-id="24461-112">如[什麼是量子運算？](xref:microsoft.quantum.overview.what)文中所述，量子位元是一種可疊加的量子資訊單位。</span><span class="sxs-lookup"><span data-stu-id="24461-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="24461-113">測量時，量子位元只能是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="24461-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="24461-114">不過在執行期間，量子位元的狀態代表著測量讀數為 0 或 1 的機率。</span><span class="sxs-lookup"><span data-stu-id="24461-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="24461-115">這個概率性的狀態稱為疊加。</span><span class="sxs-lookup"><span data-stu-id="24461-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="24461-116">我們可以使用此機率來產生亂數。</span><span class="sxs-lookup"><span data-stu-id="24461-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="24461-117">在我們的 Q# 作業中，我們引進 Q# 原生的 `Qubit` 資料類型。</span><span class="sxs-lookup"><span data-stu-id="24461-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="24461-118">我們只能使用 `using` 陳述式來配置 `Qubit`。</span><span class="sxs-lookup"><span data-stu-id="24461-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="24461-119">當量子位元獲得配置時，一定會處於 `Zero` 狀態。</span><span class="sxs-lookup"><span data-stu-id="24461-119">When it gets allocated a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="24461-120">使用 `H` 作業，我們可以將 `Qubit` 置於疊加狀態。</span><span class="sxs-lookup"><span data-stu-id="24461-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="24461-121">若要測量量子位元並讀取其值，請使用 `M` 內建作業。</span><span class="sxs-lookup"><span data-stu-id="24461-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="24461-122">藉由將 `Qubit` 置於疊加並加以測量，每次叫用程式碼時，結果就會是不同的值。</span><span class="sxs-lookup"><span data-stu-id="24461-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="24461-123">解除配置 `Qubit` 時，必須將它明確設定回 `Zero` 狀態，否則模擬器將會報告執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="24461-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="24461-124">叫用 `Reset` 是達成此動作的簡單做法。</span><span class="sxs-lookup"><span data-stu-id="24461-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="24461-125">使用布洛赫球體將程式碼視覺化</span><span class="sxs-lookup"><span data-stu-id="24461-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="24461-126">在布洛赫球體中，北極點代表古典值 **0**，而南極點代表古典值 **1**。</span><span class="sxs-lookup"><span data-stu-id="24461-126">In the Bloch sphere the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="24461-127">任何疊加都可以用球體上的點表示 (以箭頭表示)。</span><span class="sxs-lookup"><span data-stu-id="24461-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="24461-128">當箭頭末端愈接近極點時，量子位元在測量時塌縮為指派給該極點的古典值的機率愈高。</span><span class="sxs-lookup"><span data-stu-id="24461-128">When the closer the end of the arrow to a pole, the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="24461-129">例如，下面紅色箭頭所表示的量子位元 狀態，在我們測量它時有較高的機率是 **0** 值。</span><span class="sxs-lookup"><span data-stu-id="24461-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="./Bloch.svg" width="175">

<span data-ttu-id="24461-130">我們可以用這個表示方式來將程式碼的作用視覺化呈現：</span><span class="sxs-lookup"><span data-stu-id="24461-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="24461-131">首先，我們讓量子位元的初始狀態為 **0**，並套用 `H` 來建立疊加，疊加的 **0** 和 **1** 機率相同。</span><span class="sxs-lookup"><span data-stu-id="24461-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="./H.svg" width="450">

* <span data-ttu-id="24461-132">然後，我們測量量子位元並儲存輸出：</span><span class="sxs-lookup"><span data-stu-id="24461-132">Then we measure the qubit and save the output:</span></span>

<img src="./Measurement2.svg" width="450">

<span data-ttu-id="24461-133">由於測量的結果完全隨機，我們便能得到一個隨機位元。</span><span class="sxs-lookup"><span data-stu-id="24461-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="24461-134">我們可以呼叫此函式多次來建立整數。</span><span class="sxs-lookup"><span data-stu-id="24461-134">We can call this function several times to create integers.</span></span> <span data-ttu-id="24461-135">例如，如果我們呼叫此函式三次來取得三個隨機位元，則可以建立隨機的 3位元數字 (也就是介於 0 和 7 之間的亂數)。</span><span class="sxs-lookup"><span data-stu-id="24461-135">For example, if we call the function three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>