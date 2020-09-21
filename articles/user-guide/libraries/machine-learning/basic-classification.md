---
title: 量子 Machine Learning 程式庫的基本分類
description: 瞭解如何 Q# 使用 MICROSOFT QDK 的量子 Machine Learning 程式庫，執行以所撰寫的量子順序分類器。
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5dc4614b9992e2c6b9f8ff4b839c0929ec8cab7c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833711"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="51f04-103">基本分類：使用 QDK 分類資料</span><span class="sxs-lookup"><span data-stu-id="51f04-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="51f04-104">在本快速入門中，您將瞭解如何使用 QDK 的量子 Machine Learning 程式庫，執行以所撰寫的量子順序分類器 Q# 。</span><span class="sxs-lookup"><span data-stu-id="51f04-104">In this Quickstart, you will learn how to run a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="51f04-105">在本指南中，我們將使用中定義的分類器結構來使用半衛星資料集 Q# 。</span><span class="sxs-lookup"><span data-stu-id="51f04-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="51f04-106">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="51f04-106">Prerequisites</span></span>

- <span data-ttu-id="51f04-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="51f04-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="51f04-108">Q#為[Python 主機程式](xref:microsoft.quantum.install.python)或[c # 主機程式](xref:microsoft.quantum.install.cs)建立專案。</span><span class="sxs-lookup"><span data-stu-id="51f04-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="51f04-109">主機程式</span><span class="sxs-lookup"><span data-stu-id="51f04-109">Host program</span></span>

<span data-ttu-id="51f04-110">您的主機程式是由三個部分所組成：</span><span class="sxs-lookup"><span data-stu-id="51f04-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="51f04-111">載入資料集，然後為您的模型選擇一組起始參數。</span><span class="sxs-lookup"><span data-stu-id="51f04-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="51f04-112">執行定型以判斷模型的參數和偏差。</span><span class="sxs-lookup"><span data-stu-id="51f04-112">Run training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="51f04-113">驗證模型以判斷其精確度</span><span class="sxs-lookup"><span data-stu-id="51f04-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="51f04-114">使用 Visual Studio Code 或命令列的 Python</span><span class="sxs-lookup"><span data-stu-id="51f04-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="51f04-115">若要執行您是 Q# Python 的分類器，請將下列程式碼儲存為 `host.py` 。</span><span class="sxs-lookup"><span data-stu-id="51f04-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="51f04-116">請記住，您也需要 Q# `Training.qs` 本教學課程稍後說明的檔案。</span><span class="sxs-lookup"><span data-stu-id="51f04-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="51f04-117">然後，您可以從命令列執行 Python 主機程式：</span><span class="sxs-lookup"><span data-stu-id="51f04-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="51f04-118">使用 Visual Studio Code 或命令列的 C#</span><span class="sxs-lookup"><span data-stu-id="51f04-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="51f04-119">若要執行您是 Q# c # 的分類器，請將下列程式碼儲存為 `Host.cs` 。</span><span class="sxs-lookup"><span data-stu-id="51f04-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="51f04-120">請記住，您也需要 Q# `Training.qs` 本教學課程稍後說明的檔案。</span><span class="sxs-lookup"><span data-stu-id="51f04-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="51f04-121">然後，您可以從命令列執行 C# 主機程式：</span><span class="sxs-lookup"><span data-stu-id="51f04-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="51f04-122">使用 Visual Studio 2019 的 C#</span><span class="sxs-lookup"><span data-stu-id="51f04-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="51f04-123">若要 Q# 在 Visual Studio 中從 c # 執行新程式，請修改 `Host.cs` 以包含下列 c # 程式碼。</span><span class="sxs-lookup"><span data-stu-id="51f04-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="51f04-124">請記住，您也需要 Q# `Training.qs` 本教學課程稍後說明的檔案。</span><span class="sxs-lookup"><span data-stu-id="51f04-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="51f04-125">按下 F5 鍵，程式就會開始執行。</span><span class="sxs-lookup"><span data-stu-id="51f04-125">Press F5, and the program will start to run.</span></span> <span data-ttu-id="51f04-126">新視窗會顯示下列結果：</span><span class="sxs-lookup"><span data-stu-id="51f04-126">A new window will display the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="51f04-127">Q \# 分類程式代碼</span><span class="sxs-lookup"><span data-stu-id="51f04-127">Q\# classifier code</span></span>

<span data-ttu-id="51f04-128">現在讓我們看看如何定義主機程式叫用的作業 Q# 。</span><span class="sxs-lookup"><span data-stu-id="51f04-128">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="51f04-129">我們會將下列程式碼儲存在名為的檔案中 `Training.qs` 。</span><span class="sxs-lookup"><span data-stu-id="51f04-129">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="51f04-130">上述程式碼中定義的最重要函數和作業如下：</span><span class="sxs-lookup"><span data-stu-id="51f04-130">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="51f04-131">`ClassifierStructure() : ControlledRotation[]` ：在此函式中，我們會藉由新增我們所考慮之受控制閘道的層級，來設定電路模型的結構。</span><span class="sxs-lookup"><span data-stu-id="51f04-131">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="51f04-132">此步驟類似于連續深度學習模型中的神經層級聲明。</span><span class="sxs-lookup"><span data-stu-id="51f04-132">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="51f04-133">`TrainHalfMoonModel() : (Double[], Double)` ：這項作業是程式碼的核心部分，並定義定型。</span><span class="sxs-lookup"><span data-stu-id="51f04-133">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="51f04-134">在這裡，我們會從程式庫中所包含的資料集載入範例、為定型設定超參數和初始參數，然後藉由呼叫程式庫中所包含的作業來開始定型 `TrainSequentialClassifier` 。</span><span class="sxs-lookup"><span data-stu-id="51f04-134">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="51f04-135">它會輸出決定分類器的參數和偏差。</span><span class="sxs-lookup"><span data-stu-id="51f04-135">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="51f04-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` ：此作業會定義用來評估模型的驗證程式。</span><span class="sxs-lookup"><span data-stu-id="51f04-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="51f04-137">在這裡，我們會載入驗證範例、每個樣本的度量數目和容錯。</span><span class="sxs-lookup"><span data-stu-id="51f04-137">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="51f04-138">它會輸出所選樣本批次的情形數目以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="51f04-138">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="51f04-139">後續步驟</span><span class="sxs-lookup"><span data-stu-id="51f04-139">Next steps</span></span>

<span data-ttu-id="51f04-140">首先，您可以使用程式碼，並嘗試變更某些參數，以查看它對定型的影響。</span><span class="sxs-lookup"><span data-stu-id="51f04-140">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="51f04-141">然後，在下一個教學課程中， [設計您自己的分類器](xref:microsoft.quantum.libraries.machine-learning.design)，您將學習如何定義分類器的結構。</span><span class="sxs-lookup"><span data-stu-id="51f04-141">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
