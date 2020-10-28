---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699696"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="8662b-102">CombinedStructure 函式</span><span class="sxs-lookup"><span data-stu-id="8662b-102">CombinedStructure function</span></span>

<span data-ttu-id="8662b-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8662b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="8662b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8662b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8662b-105">如果有一或多個控制的旋轉層級，則會傳回具有模型參數索引移位的單一圖層，讓不同的圖層以相異模型參數參數化。</span><span class="sxs-lookup"><span data-stu-id="8662b-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="8662b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="8662b-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="8662b-107">圖層： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="8662b-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="8662b-108">要合併的圖層。</span><span class="sxs-lookup"><span data-stu-id="8662b-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="8662b-109">輸出： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="8662b-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="8662b-110">一層控制的旋轉，表示所有其他圖層的串連。</span><span class="sxs-lookup"><span data-stu-id="8662b-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>