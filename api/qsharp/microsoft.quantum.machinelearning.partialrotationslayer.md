---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: e230df9b28c59e1d532d5b36adf90efa01f0f33e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852926"
---
# <a name="partialrotationslayer-function"></a><span data-ttu-id="6b3ff-102">PartialRotationsLayer 函式</span><span class="sxs-lookup"><span data-stu-id="6b3ff-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="6b3ff-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6b3ff-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6b3ff-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6b3ff-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="6b3ff-105">傳回以相異模型參數參數化之指定軸的單一量子位旋轉陣列。</span><span class="sxs-lookup"><span data-stu-id="6b3ff-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="6b3ff-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6b3ff-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="6b3ff-107">idxsQubits： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6b3ff-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6b3ff-108">要當做每個旋轉目標使用之量子位的索引。</span><span class="sxs-lookup"><span data-stu-id="6b3ff-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="6b3ff-109">軸： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="6b3ff-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="6b3ff-110">給定圖層中每個旋轉的旋轉軸。</span><span class="sxs-lookup"><span data-stu-id="6b3ff-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="6b3ff-111">輸出： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="6b3ff-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="6b3ff-112">特定軸的受控制旋轉陣列，每個量子位都有一個 `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="6b3ff-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>