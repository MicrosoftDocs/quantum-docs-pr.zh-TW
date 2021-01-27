---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: b8ec007202c8e63dc2e98d0c752f6ba1a453e236
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847407"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="f5f86-102">CombinedStructure 函式</span><span class="sxs-lookup"><span data-stu-id="f5f86-102">CombinedStructure function</span></span>

<span data-ttu-id="f5f86-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f5f86-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f5f86-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f5f86-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="f5f86-105">如果有一或多個控制的旋轉層級，則會傳回具有模型參數索引移位的單一圖層，讓不同的圖層以相異模型參數參數化。</span><span class="sxs-lookup"><span data-stu-id="f5f86-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="f5f86-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f5f86-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="f5f86-107">圖層： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="f5f86-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="f5f86-108">要合併的圖層。</span><span class="sxs-lookup"><span data-stu-id="f5f86-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="f5f86-109">輸出： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="f5f86-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="f5f86-110">一層控制的旋轉，表示所有其他圖層的串連。</span><span class="sxs-lookup"><span data-stu-id="f5f86-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>

## <a name="example"></a><span data-ttu-id="f5f86-111">範例</span><span class="sxs-lookup"><span data-stu-id="f5f86-111">Example</span></span>

<span data-ttu-id="f5f86-112">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="f5f86-112">The following are equivalent:</span></span>

```qsharp
let structure = CombinedStructure([
    LocalRotationLayer(2, PauliY),
    CyclicEntanglingLayer(3, PauliX, 2)
]);
let structure = [
    ControlledRotation((0, new Int[0]), PauliY, 0),
    ControlledRotation((1, new Int[0]), PauliY, 1),
    ControlledRotation((0, [2]), PauliX, 2),
    ControlledRotation((1, [0]), PauliX, 3),
    ControlledRotation((2, [1]), PauliX, 4)
];
```