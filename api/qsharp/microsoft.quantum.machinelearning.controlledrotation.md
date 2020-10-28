---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697691"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="e5b69-102">ControlledRotation 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="e5b69-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="e5b69-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e5b69-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e5b69-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5b69-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5b69-105">描述以其目標和控制索引、旋轉軸和索引至模型參數向量的控制旋轉。</span><span class="sxs-lookup"><span data-stu-id="e5b69-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="e5b69-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="e5b69-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="e5b69-107">TargetIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5b69-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e5b69-108">此受控制旋轉之目標量子位的索引。</span><span class="sxs-lookup"><span data-stu-id="e5b69-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="e5b69-109">ControlIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e5b69-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e5b69-110">這項旋轉的控制項量子位索引陣列。</span><span class="sxs-lookup"><span data-stu-id="e5b69-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="e5b69-111">軸： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="e5b69-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="e5b69-112">此旋轉的軸。</span><span class="sxs-lookup"><span data-stu-id="e5b69-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="e5b69-113">ParameterIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5b69-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e5b69-114">模型參數向量的索引，描述這個旋轉的角度。</span><span class="sxs-lookup"><span data-stu-id="e5b69-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5b69-115">備註</span><span class="sxs-lookup"><span data-stu-id="e5b69-115">Remarks</span></span>

<span data-ttu-id="e5b69-116">您可以設定 `ControlIndices` 為空的索引陣列來表示無法控制的旋轉 `new Int[0]` 。</span><span class="sxs-lookup"><span data-stu-id="e5b69-116">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>