---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700258"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="f5203-102">SequentialModel 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="f5203-102">SequentialModel user defined type</span></span>

<span data-ttu-id="f5203-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f5203-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f5203-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5203-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5203-105">描述由一系列的參數化和控制的旋轉、旋轉角度的指派，以及模型辨識的兩個類別之間的偏差所組成的量子分類器模型。</span><span class="sxs-lookup"><span data-stu-id="f5203-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="f5203-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="f5203-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="f5203-107">結構： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="f5203-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="f5203-108">用來分類輸入的受控旋轉序列。</span><span class="sxs-lookup"><span data-stu-id="f5203-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="f5203-109">參數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f5203-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f5203-110">指派給指定分類結構的旋轉角度。</span><span class="sxs-lookup"><span data-stu-id="f5203-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="f5203-111">偏差： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f5203-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f5203-112">此分類器所辨識的兩個類別之間的偏差。</span><span class="sxs-lookup"><span data-stu-id="f5203-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="f5203-113">參考</span><span class="sxs-lookup"><span data-stu-id="f5203-113">References</span></span>

- [<span data-ttu-id="f5203-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="f5203-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)