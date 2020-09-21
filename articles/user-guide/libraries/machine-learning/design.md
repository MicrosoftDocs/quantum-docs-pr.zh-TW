---
title: 使用 QDK 設計您自己的分類器
description: 瞭解為量子線路中心分類器設計電路模型的基本概念。
author: geduardo
ms.author: v-edsanc
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3515279dd4d03b2a512035af0b13e084dd91f9dc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835701"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="df145-103">設計您自己的分類器</span><span class="sxs-lookup"><span data-stu-id="df145-103">Design your own classifier</span></span>

<span data-ttu-id="df145-104">在本指南中，您將瞭解以量子線路為中心的分類器之電路模型設計背後的基本概念。</span><span class="sxs-lookup"><span data-stu-id="df145-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="df145-105">如同傳統深度學習，沒有選擇特定架構的一般規則。</span><span class="sxs-lookup"><span data-stu-id="df145-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="df145-106">視問題而定，某些架構會比其他架構執行得更好。</span><span class="sxs-lookup"><span data-stu-id="df145-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="df145-107">但在設計線路時，有些概念可能很有用：</span><span class="sxs-lookup"><span data-stu-id="df145-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="df145-108">大量的參數表示更有彈性的模型，這可能適合用來繪製複雜的分類界限，但也可能更容易過度學習。</span><span class="sxs-lookup"><span data-stu-id="df145-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="df145-109">量子位之間的 Entangling 閘道對於捕捉量子功能之間的相互關聯是不可或缺的。</span><span class="sxs-lookup"><span data-stu-id="df145-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="df145-110">如何使用 Q 建立分類器\#</span><span class="sxs-lookup"><span data-stu-id="df145-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="df145-111">為了建立分類器，我們將會在電路模型中串連參數化控制的旋轉。</span><span class="sxs-lookup"><span data-stu-id="df145-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="df145-112">若要這樣做，我們可以使用 [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) 量子 Machine Learning 程式庫中定義的類型。</span><span class="sxs-lookup"><span data-stu-id="df145-112">To do it we can use the type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="df145-113">這個型別接受四個引數來決定：目標量子位的索引、控制項量子位的索引陣列、旋轉軸，以及定義模型的參數陣列中相關聯參數的索引。</span><span class="sxs-lookup"><span data-stu-id="df145-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="df145-114">讓我們看看分類器的範例。</span><span class="sxs-lookup"><span data-stu-id="df145-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="df145-115">在 [半衛星範例](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons)中，我們可以在檔案中找到下列定義的分類器 `Training.qs` 。</span><span class="sxs-lookup"><span data-stu-id="df145-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

<span data-ttu-id="df145-116">我們在這裡定義的是一種函式，它會傳回 `ControlledRotation` 元素陣列，連同參數陣列，而偏差將會定義我們的 [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) 。</span><span class="sxs-lookup"><span data-stu-id="df145-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span></span> <span data-ttu-id="df145-117">這種類型在量子 Machine Learning 程式庫中是基本的，而且會定義分類器。</span><span class="sxs-lookup"><span data-stu-id="df145-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="df145-118">上述函數中定義的電路是分類器的一部分，其中資料集的每個範例都包含兩項功能。</span><span class="sxs-lookup"><span data-stu-id="df145-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="df145-119">因此，我們只需要兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="df145-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="df145-120">電路的圖形標記法如下：</span><span class="sxs-lookup"><span data-stu-id="df145-120">The graphical representation of the circuit is:</span></span>

 ![電路模型範例](~/media/circuit_model_1.PNG)

<span data-ttu-id="df145-122">請注意，根據預設，量子 Machine Learning 程式庫的作業會測量註冊的最後一個量子位，以估計分類機率。</span><span class="sxs-lookup"><span data-stu-id="df145-122">Note that by default the operations of the Quantum Machine Learning library measure the last qubit of the register to estimate the classification probabilities.</span></span> <span data-ttu-id="df145-123">當您設計線路時，請記住這一點。</span><span class="sxs-lookup"><span data-stu-id="df145-123">You should keep in mind this fact when designing your circuit.</span></span>

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="df145-124">使用程式庫函數來寫入閘道層</span><span class="sxs-lookup"><span data-stu-id="df145-124">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="df145-125">假設我們的資料集具有每個實例784的功能，例如28×28圖元的影像，例如 MNIST 資料集。</span><span class="sxs-lookup"><span data-stu-id="df145-125">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="df145-126">在此情況下，線路的寬度會變得夠大，因此以手動方式撰寫每個閘道會成為可能但不實用的工作。</span><span class="sxs-lookup"><span data-stu-id="df145-126">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="df145-127">這就是量子 Machine Learning 程式庫提供一組工具來自動產生參數化旋轉層級的原因。</span><span class="sxs-lookup"><span data-stu-id="df145-127">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="df145-128">例如，此函式會在 [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) 指定的軸上傳回未受控制的單一量子位旋轉陣列，其中每個量子位都有一個旋轉，而每個都是由不同的模型參數所參數化。</span><span class="sxs-lookup"><span data-stu-id="df145-128">For instance, the function [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="df145-129">例如，會傳回 `LocalRotationsLayer(4, X)` 下列一組閘道：</span><span class="sxs-lookup"><span data-stu-id="df145-129">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![本機旋轉圖層](~/media/local_rotations_layer.PNG)

<span data-ttu-id="df145-131">建議您探索 [量子 Machine Learning 程式庫的 API 參考](xref:microsoft.quantum.machinelearning) ，以探索可簡化電路設計的所有工具。</span><span class="sxs-lookup"><span data-stu-id="df145-131">We recommend you explore the [API reference of the Quantum Machine Learning library](xref:microsoft.quantum.machinelearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="df145-132">後續步驟</span><span class="sxs-lookup"><span data-stu-id="df145-132">Next steps</span></span>

 <span data-ttu-id="df145-133">在範例所提供的範例中，嘗試不同的結構。</span><span class="sxs-lookup"><span data-stu-id="df145-133">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="df145-134">您是否看到模型效能的任何變更？</span><span class="sxs-lookup"><span data-stu-id="df145-134">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="df145-135">在下一個教學課程中， [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) 您將瞭解如何載入資料集，以嘗試及探索新的分類器架構。</span><span class="sxs-lookup"><span data-stu-id="df145-135">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>
