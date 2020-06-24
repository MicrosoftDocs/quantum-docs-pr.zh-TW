---
title: 使用配量 Machine Learning 程式庫的基本分類
description: '瞭解如何使用 Microsoft QDK 的量子 Machine Learning 程式庫，執行以 Q # 撰寫的量子順序分類器。'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: 1d2538fd164c4c61c2712978d3b5c57b0eb766e6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274627"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="54394-103">基本分類：使用 QDK 將資料分類</span><span class="sxs-lookup"><span data-stu-id="54394-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="54394-104">在本快速入門中，您將瞭解如何使用 QDK 的量子 Machine Learning 程式庫，執行以 Q # 撰寫的量子順序分類器。</span><span class="sxs-lookup"><span data-stu-id="54394-104">In this Quickstart, you will learn how to execute a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="54394-105">在本指南中，我們將使用在 Q # 中定義的分類器結構來使用半月球資料集。</span><span class="sxs-lookup"><span data-stu-id="54394-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="54394-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="54394-106">Prerequisites</span></span>

- <span data-ttu-id="54394-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="54394-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="54394-108">建立適用于[Python 主機程式](xref:microsoft.quantum.install.python)或[c # 主機程式](xref:microsoft.quantum.install.cs)的 Q # 專案。</span><span class="sxs-lookup"><span data-stu-id="54394-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="54394-109">主機程式</span><span class="sxs-lookup"><span data-stu-id="54394-109">Host program</span></span>

<span data-ttu-id="54394-110">您的主機套裝程式含三個部分：</span><span class="sxs-lookup"><span data-stu-id="54394-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="54394-111">載入資料集，並為您的模型選擇一組起始參數。</span><span class="sxs-lookup"><span data-stu-id="54394-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="54394-112">執行訓練來判斷模型的參數和偏差。</span><span class="sxs-lookup"><span data-stu-id="54394-112">Execute training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="54394-113">驗證模型以判斷其正確性</span><span class="sxs-lookup"><span data-stu-id="54394-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="54394-114">使用 Visual Studio Code 或命令列的 Python</span><span class="sxs-lookup"><span data-stu-id="54394-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="54394-115">若要執行，您是來自 Python 的 Q # 分類器，請將下列程式碼儲存為 `host.py` 。</span><span class="sxs-lookup"><span data-stu-id="54394-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="54394-116">請記住，您也需要在 `Training.qs` 本教學課程稍後說明的 Q # 檔案。</span><span class="sxs-lookup"><span data-stu-id="54394-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="54394-117">然後，您可以從命令列執行 Python 主機程式：</span><span class="sxs-lookup"><span data-stu-id="54394-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="54394-118">使用 Visual Studio Code 或命令列的 C#</span><span class="sxs-lookup"><span data-stu-id="54394-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="54394-119">若要執行，您是 c # 的 Q # 分類器，請將下列程式碼儲存為 `Host.cs` 。</span><span class="sxs-lookup"><span data-stu-id="54394-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="54394-120">請記住，您也需要在 `Training.qs` 本教學課程稍後說明的 Q # 檔案。</span><span class="sxs-lookup"><span data-stu-id="54394-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="54394-121">然後，您可以從命令列執行 C# 主機程式：</span><span class="sxs-lookup"><span data-stu-id="54394-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="54394-122">使用 Visual Studio 2019 的 C#</span><span class="sxs-lookup"><span data-stu-id="54394-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="54394-123">若要從 Visual Studio 中的 c # 執行新的 Q # 程式，請修改 `Host.cs` 以包含下列 c # 程式碼。</span><span class="sxs-lookup"><span data-stu-id="54394-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="54394-124">請記住，您也需要在 `Training.qs` 本教學課程稍後說明的 Q # 檔案。</span><span class="sxs-lookup"><span data-stu-id="54394-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="54394-125">然後按 F5 鍵，程式會開始執行，並跳出一個新視窗顯示下列結果：</span><span class="sxs-lookup"><span data-stu-id="54394-125">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="54394-126">Q \# 分類器程式碼</span><span class="sxs-lookup"><span data-stu-id="54394-126">Q\# classifier code</span></span>

<span data-ttu-id="54394-127">現在讓我們來看看如何在 Q # 中定義主機程式所叫用的作業。</span><span class="sxs-lookup"><span data-stu-id="54394-127">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="54394-128">我們會將下列程式碼儲存在名為的檔案中 `Training.qs` 。</span><span class="sxs-lookup"><span data-stu-id="54394-128">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="54394-129">上述程式碼中所定義的最重要函式和作業如下：</span><span class="sxs-lookup"><span data-stu-id="54394-129">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="54394-130">`ClassifierStructure() : ControlledRotation[]`：在此函式中，我們會藉由新增我們所考慮之受控制閘道的層級，來設定線路模型的結構。</span><span class="sxs-lookup"><span data-stu-id="54394-130">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="54394-131">此步驟類似于連續深度學習模型中的神經層級宣告。</span><span class="sxs-lookup"><span data-stu-id="54394-131">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="54394-132">`TrainHalfMoonModel() : (Double[], Double)`：此作業是程式碼的核心部分，會定義定型。</span><span class="sxs-lookup"><span data-stu-id="54394-132">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="54394-133">在這裡，我們會從程式庫中包含的資料集載入範例，我們會設定定型的超參數和初始參數，並藉由呼叫程式庫中包含的作業來開始定型 `TrainSequentialClassifier` 。</span><span class="sxs-lookup"><span data-stu-id="54394-133">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="54394-134">它會輸出參數和判斷分類器的偏差。</span><span class="sxs-lookup"><span data-stu-id="54394-134">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="54394-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`：此作業會定義用來評估模型的驗證程式。</span><span class="sxs-lookup"><span data-stu-id="54394-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="54394-136">在這裡，我們會載入用於驗證的範例、每個樣本的度量數目和容錯。</span><span class="sxs-lookup"><span data-stu-id="54394-136">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="54394-137">它會輸出所選樣本批次的 misclassifications 數目以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="54394-137">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="54394-138">後續步驟</span><span class="sxs-lookup"><span data-stu-id="54394-138">Next steps</span></span>

<span data-ttu-id="54394-139">首先，您可以使用程式碼，並嘗試變更某些參數，以查看它對定型的影響。</span><span class="sxs-lookup"><span data-stu-id="54394-139">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="54394-140">接著，在下一個教學課程中，[設計您自己的分類器](xref:microsoft.quantum.libraries.machine-learning.design)，您將學習如何定義分類器的結構。</span><span class="sxs-lookup"><span data-stu-id="54394-140">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
