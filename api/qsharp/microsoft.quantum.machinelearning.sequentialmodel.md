---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196169"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="3e460-102">SequentialModel 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="3e460-102">SequentialModel user defined type</span></span>

<span data-ttu-id="3e460-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3e460-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3e460-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3e460-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="3e460-105">描述由一系列的參數化和控制的旋轉、旋轉角度的指派，以及模型辨識的兩個類別之間的偏差所組成的量子分類器模型。</span><span class="sxs-lookup"><span data-stu-id="3e460-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="3e460-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="3e460-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="3e460-107">結構： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="3e460-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="3e460-108">用來分類輸入的受控旋轉序列。</span><span class="sxs-lookup"><span data-stu-id="3e460-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="3e460-109">參數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3e460-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3e460-110">指派給指定分類結構的旋轉角度。</span><span class="sxs-lookup"><span data-stu-id="3e460-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="3e460-111">偏差： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3e460-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3e460-112">此分類器所辨識的兩個類別之間的偏差。</span><span class="sxs-lookup"><span data-stu-id="3e460-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="3e460-113">參考</span><span class="sxs-lookup"><span data-stu-id="3e460-113">References</span></span>

- [<span data-ttu-id="3e460-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="3e460-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)