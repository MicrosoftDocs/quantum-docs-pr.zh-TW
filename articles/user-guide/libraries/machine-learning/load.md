---
title: 載入傳統資料
description: 瞭解如何載入您自己的資料集，以使用 Microsoft 量子開發工具組 (QDK) 來定型分類器模型。
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7ebfe085e50d4647fdb1027250cf3134f8d8f8c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856462"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="c9541-103">載入和分類您自己的資料集</span><span class="sxs-lookup"><span data-stu-id="c9541-103">Load and classify your own datasets</span></span>

<span data-ttu-id="c9541-104">在這個簡短的教學課程中，我們將瞭解如何載入您自己的資料集，以使用量子開發工具組 (QDK) 來定型分類器模型。</span><span class="sxs-lookup"><span data-stu-id="c9541-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="c9541-105">強烈建議您使用標準化的序列化格式，例如 [JSON](https://en.wikipedia.org/wiki/JSON) 檔案來儲存您的資料。</span><span class="sxs-lookup"><span data-stu-id="c9541-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="c9541-106">這類格式提供與 Python 和 .NET 生態系統等不同架構的高度相容性。</span><span class="sxs-lookup"><span data-stu-id="c9541-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="c9541-107">尤其是，我們建議使用我們的範本來載入資料，如此您就可以直接從範例複製並貼上程式碼。</span><span class="sxs-lookup"><span data-stu-id="c9541-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="c9541-108">載入資料集的範本</span><span class="sxs-lookup"><span data-stu-id="c9541-108">Template for loading your datasets</span></span>

<span data-ttu-id="c9541-109">假設我們有一個訓練資料集 $ (x，y) $ 大小 $N = $2，其中每個實例 $x _i $ of $x $ 有三個功能： $x _ {i1} $、$x _ {i2} $ 和 $x _ {i3} $。</span><span class="sxs-lookup"><span data-stu-id="c9541-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="c9541-110">驗證資料集具有相同的結構。</span><span class="sxs-lookup"><span data-stu-id="c9541-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="c9541-111">這些底下可以使用 `data.json` 類似下列的檔案來表示：</span><span class="sxs-lookup"><span data-stu-id="c9541-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a><span data-ttu-id="c9541-112">使用範本的範例</span><span class="sxs-lookup"><span data-stu-id="c9541-112">Example using the template</span></span>

<span data-ttu-id="c9541-113">假設我們有一個小型資料集，其具有不同貓和狗的高度和加權。</span><span class="sxs-lookup"><span data-stu-id="c9541-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="c9541-114">這個資料集很小，無法定型模型，但也足以顯示載入資料集的程式。</span><span class="sxs-lookup"><span data-stu-id="c9541-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="c9541-115">高度 (m) </span><span class="sxs-lookup"><span data-stu-id="c9541-115">Height (m)</span></span> | <span data-ttu-id="c9541-116">重量 (公斤)</span><span class="sxs-lookup"><span data-stu-id="c9541-116">Weight (kg)</span></span> | <span data-ttu-id="c9541-117">動物</span><span class="sxs-lookup"><span data-stu-id="c9541-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="c9541-118">0.54</span><span class="sxs-lookup"><span data-stu-id="c9541-118">0.54</span></span>      | <span data-ttu-id="c9541-119">30</span><span class="sxs-lookup"><span data-stu-id="c9541-119">30</span></span>         | <span data-ttu-id="c9541-120">狗</span><span class="sxs-lookup"><span data-stu-id="c9541-120">Dog</span></span>    |
| <span data-ttu-id="c9541-121">0.30</span><span class="sxs-lookup"><span data-stu-id="c9541-121">0.30</span></span>      | <span data-ttu-id="c9541-122">8</span><span class="sxs-lookup"><span data-stu-id="c9541-122">8</span></span>          | <span data-ttu-id="c9541-123">貓</span><span class="sxs-lookup"><span data-stu-id="c9541-123">Cat</span></span>    |
| <span data-ttu-id="c9541-124">0.91</span><span class="sxs-lookup"><span data-stu-id="c9541-124">0.91</span></span>      | <span data-ttu-id="c9541-125">44</span><span class="sxs-lookup"><span data-stu-id="c9541-125">44</span></span>         | <span data-ttu-id="c9541-126">狗</span><span class="sxs-lookup"><span data-stu-id="c9541-126">Dog</span></span>    |
| <span data-ttu-id="c9541-127">0.86</span><span class="sxs-lookup"><span data-stu-id="c9541-127">0.86</span></span>      | <span data-ttu-id="c9541-128">31</span><span class="sxs-lookup"><span data-stu-id="c9541-128">31</span></span>          | <span data-ttu-id="c9541-129">狗</span><span class="sxs-lookup"><span data-stu-id="c9541-129">Dog</span></span>    |
| <span data-ttu-id="c9541-130">0.32</span><span class="sxs-lookup"><span data-stu-id="c9541-130">0.32</span></span>      | <span data-ttu-id="c9541-131">5</span><span class="sxs-lookup"><span data-stu-id="c9541-131">5</span></span>         | <span data-ttu-id="c9541-132">貓</span><span class="sxs-lookup"><span data-stu-id="c9541-132">Cat</span></span>    |
| <span data-ttu-id="c9541-133">0.25</span><span class="sxs-lookup"><span data-stu-id="c9541-133">0.25</span></span>      | <span data-ttu-id="c9541-134">4</span><span class="sxs-lookup"><span data-stu-id="c9541-134">4</span></span>          | <span data-ttu-id="c9541-135">貓</span><span class="sxs-lookup"><span data-stu-id="c9541-135">Cat</span></span>    |

<span data-ttu-id="c9541-136">程序如下：</span><span class="sxs-lookup"><span data-stu-id="c9541-136">The process is:</span></span>

- <span data-ttu-id="c9541-137">首先，我們需要將資料集分成定型和驗證。</span><span class="sxs-lookup"><span data-stu-id="c9541-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="c9541-138">在此情況下，我們可以採用前三個範例來進行訓練，並使用其餘範例進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c9541-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="c9541-139">一般而言，若要隨機取樣定型和驗證資料集，以避免定型資料中有不必要的偏差，通常是很好的作法。</span><span class="sxs-lookup"><span data-stu-id="c9541-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="c9541-140">其次，我們需要將數值標籤指派給每個類別。</span><span class="sxs-lookup"><span data-stu-id="c9541-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="c9541-141">請注意，目前 QML 程式庫只會認可二元分類問題。</span><span class="sxs-lookup"><span data-stu-id="c9541-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="c9541-142">因此，我們會將標籤0指派給類別 `Dog` ，並將數位1指派給類別 `Cat` 。</span><span class="sxs-lookup"><span data-stu-id="c9541-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="c9541-143">最後，我們會使用資料集的資料來填滿範本。</span><span class="sxs-lookup"><span data-stu-id="c9541-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="c9541-144">請注意，對於大型資料集，您應該建立一個小型的腳本，以自動從您的特定資料集產生範本。</span><span class="sxs-lookup"><span data-stu-id="c9541-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="c9541-145">此腳本將取決於您的資料集原始格式。</span><span class="sxs-lookup"><span data-stu-id="c9541-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="c9541-146">針對我們的資料集，檔案 `data.json` 為：</span><span class="sxs-lookup"><span data-stu-id="c9541-146">For our dataset the `data.json` file is:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a><span data-ttu-id="c9541-147">載入資料</span><span class="sxs-lookup"><span data-stu-id="c9541-147">Loading the data</span></span>

<span data-ttu-id="c9541-148">當您將資料序列化為 JSON 檔案之後，您可以使用您選擇的主機語言提供的 JSON 程式庫將它載入。</span><span class="sxs-lookup"><span data-stu-id="c9541-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="c9541-149">Python</span><span class="sxs-lookup"><span data-stu-id="c9541-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="c9541-150">Python 提供使用 JSON 序列化資料的 [內建 `json` 套件](https://docs.python.org/3.7/library/json.html) ：</span><span class="sxs-lookup"><span data-stu-id="c9541-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="c9541-151">C#</span><span class="sxs-lookup"><span data-stu-id="c9541-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="c9541-152">.NET Core 平臺提供使用 JSON 序列化資料的[ `System.Text.Json` 封裝](https://www.nuget.org/packages/System.Text.Json)：</span><span class="sxs-lookup"><span data-stu-id="c9541-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a><span data-ttu-id="c9541-153">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c9541-153">Next steps</span></span>

<span data-ttu-id="c9541-154">現在您已準備好開始使用您自己的資料集來執行您自己的實驗。</span><span class="sxs-lookup"><span data-stu-id="c9541-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="c9541-155">試用不同的分類器和資料集，並參與共用您的結果的社區！</span><span class="sxs-lookup"><span data-stu-id="c9541-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
