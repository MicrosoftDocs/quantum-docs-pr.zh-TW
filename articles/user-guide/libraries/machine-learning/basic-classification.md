---
title: 使用配量 Machine Learning 程式庫的基本分類
description: 瞭解如何 Q# 使用 MICROSOFT QDK 的量子 Machine Learning 程式庫來執行以撰寫的量子順序分類器。
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: f9c3e7ab85c0f0d1a6063e593607d35c5cb76936
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868962"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="8b84c-103">基本分類：使用 QDK 將資料分類</span><span class="sxs-lookup"><span data-stu-id="8b84c-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="8b84c-104">在本快速入門中，您將瞭解如何 Q# 使用 QDK 的量子 Machine Learning 程式庫，執行以撰寫的量子順序分類器。</span><span class="sxs-lookup"><span data-stu-id="8b84c-104">In this Quickstart, you will learn how to execute a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="8b84c-105">在本指南中，我們將使用中定義的分類器結構來使用半月球資料集 Q# 。</span><span class="sxs-lookup"><span data-stu-id="8b84c-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8b84c-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="8b84c-106">Prerequisites</span></span>

- <span data-ttu-id="8b84c-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="8b84c-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="8b84c-108">Q#為[Python 主機程式](xref:microsoft.quantum.install.python)或[c # 主機程式](xref:microsoft.quantum.install.cs)建立專案。</span><span class="sxs-lookup"><span data-stu-id="8b84c-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="8b84c-109">主機程式</span><span class="sxs-lookup"><span data-stu-id="8b84c-109">Host program</span></span>

<span data-ttu-id="8b84c-110">您的主機套裝程式含三個部分：</span><span class="sxs-lookup"><span data-stu-id="8b84c-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="8b84c-111">載入資料集，並為您的模型選擇一組起始參數。</span><span class="sxs-lookup"><span data-stu-id="8b84c-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="8b84c-112">執行訓練來判斷模型的參數和偏差。</span><span class="sxs-lookup"><span data-stu-id="8b84c-112">Execute training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="8b84c-113">驗證模型以判斷其正確性</span><span class="sxs-lookup"><span data-stu-id="8b84c-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="8b84c-114">使用 Visual Studio Code 或命令列的 Python</span><span class="sxs-lookup"><span data-stu-id="8b84c-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="8b84c-115">若要執行，您是 Q# Python 的分類器，請將下列程式碼儲存為 `host.py` 。</span><span class="sxs-lookup"><span data-stu-id="8b84c-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="8b84c-116">請記住，您也需要 Q# `Training.qs` 此檔案，本教學課程稍後會有說明。</span><span class="sxs-lookup"><span data-stu-id="8b84c-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="8b84c-117">然後，您可以從命令列執行 Python 主機程式：</span><span class="sxs-lookup"><span data-stu-id="8b84c-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="8b84c-118">使用 Visual Studio Code 或命令列的 C#</span><span class="sxs-lookup"><span data-stu-id="8b84c-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="8b84c-119">若要執行，您是 Q# c # 的分類器，請將下列程式碼儲存為 `Host.cs` 。</span><span class="sxs-lookup"><span data-stu-id="8b84c-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="8b84c-120">請記住，您也需要 Q# `Training.qs` 此檔案，本教學課程稍後會有說明。</span><span class="sxs-lookup"><span data-stu-id="8b84c-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="8b84c-121">然後，您可以從命令列執行 C# 主機程式：</span><span class="sxs-lookup"><span data-stu-id="8b84c-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="8b84c-122">使用 Visual Studio 2019 的 C#</span><span class="sxs-lookup"><span data-stu-id="8b84c-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="8b84c-123">若要 Q# 從 Visual Studio 中的 c # 執行新程式，請修改 `Host.cs` 以包含下列 c # 程式碼。</span><span class="sxs-lookup"><span data-stu-id="8b84c-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="8b84c-124">請記住，您也需要 Q# `Training.qs` 此檔案，本教學課程稍後會有說明。</span><span class="sxs-lookup"><span data-stu-id="8b84c-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="8b84c-125">然後按 F5 鍵，程式會開始執行，並跳出一個新視窗顯示下列結果：</span><span class="sxs-lookup"><span data-stu-id="8b84c-125">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="8b84c-126">Q \# 分類器程式碼</span><span class="sxs-lookup"><span data-stu-id="8b84c-126">Q\# classifier code</span></span>

<span data-ttu-id="8b84c-127">現在讓我們來瞭解如何在中定義主機程式所叫用的作業 Q# 。</span><span class="sxs-lookup"><span data-stu-id="8b84c-127">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="8b84c-128">我們會將下列程式碼儲存在名為的檔案中 `Training.qs` 。</span><span class="sxs-lookup"><span data-stu-id="8b84c-128">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="8b84c-129">上述程式碼中所定義的最重要函式和作業如下：</span><span class="sxs-lookup"><span data-stu-id="8b84c-129">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="8b84c-130">`ClassifierStructure() : ControlledRotation[]`：在此函式中，我們會藉由新增我們所考慮之受控制閘道的層級，來設定線路模型的結構。</span><span class="sxs-lookup"><span data-stu-id="8b84c-130">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="8b84c-131">此步驟類似于連續深度學習模型中的神經層級宣告。</span><span class="sxs-lookup"><span data-stu-id="8b84c-131">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="8b84c-132">`TrainHalfMoonModel() : (Double[], Double)`：此作業是程式碼的核心部分，會定義定型。</span><span class="sxs-lookup"><span data-stu-id="8b84c-132">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="8b84c-133">在這裡，我們會從程式庫中包含的資料集載入範例，我們會設定定型的超參數和初始參數，並藉由呼叫程式庫中包含的作業來開始定型 `TrainSequentialClassifier` 。</span><span class="sxs-lookup"><span data-stu-id="8b84c-133">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="8b84c-134">它會輸出參數和判斷分類器的偏差。</span><span class="sxs-lookup"><span data-stu-id="8b84c-134">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="8b84c-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`：此作業會定義用來評估模型的驗證程式。</span><span class="sxs-lookup"><span data-stu-id="8b84c-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="8b84c-136">在這裡，我們會載入用於驗證的範例、每個樣本的度量數目和容錯。</span><span class="sxs-lookup"><span data-stu-id="8b84c-136">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="8b84c-137">它會輸出所選樣本批次的 misclassifications 數目以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="8b84c-137">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8b84c-138">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8b84c-138">Next steps</span></span>

<span data-ttu-id="8b84c-139">首先，您可以使用程式碼，並嘗試變更某些參數，以查看它對定型的影響。</span><span class="sxs-lookup"><span data-stu-id="8b84c-139">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="8b84c-140">接著，在下一個教學課程中，[設計您自己的分類器](xref:microsoft.quantum.libraries.machine-learning.design)，您將學習如何定義分類器的結構。</span><span class="sxs-lookup"><span data-stu-id="8b84c-140">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
