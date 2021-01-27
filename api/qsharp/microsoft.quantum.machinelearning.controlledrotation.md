---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847401"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="6cd07-102">ControlledRotation 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="6cd07-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="6cd07-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6cd07-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6cd07-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6cd07-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="6cd07-105">描述以其目標和控制索引、旋轉軸和索引至模型參數向量的控制旋轉。</span><span class="sxs-lookup"><span data-stu-id="6cd07-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="6cd07-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="6cd07-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="6cd07-107">TargetIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6cd07-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6cd07-108">此受控制旋轉之目標量子位的索引。</span><span class="sxs-lookup"><span data-stu-id="6cd07-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="6cd07-109">ControlIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6cd07-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6cd07-110">這項旋轉的控制項量子位索引陣列。</span><span class="sxs-lookup"><span data-stu-id="6cd07-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="6cd07-111">軸： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="6cd07-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="6cd07-112">此旋轉的軸。</span><span class="sxs-lookup"><span data-stu-id="6cd07-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="6cd07-113">ParameterIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6cd07-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6cd07-114">模型參數向量的索引，描述這個旋轉的角度。</span><span class="sxs-lookup"><span data-stu-id="6cd07-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="example"></a><span data-ttu-id="6cd07-115">範例</span><span class="sxs-lookup"><span data-stu-id="6cd07-115">Example</span></span>

<span data-ttu-id="6cd07-116">以下代表在暫存器中第一個量子位的 $X $ 軸的旋轉、第二個量子位所控制的，以及連續模型中第四個參數所指定的角度：</span><span class="sxs-lookup"><span data-stu-id="6cd07-116">The following represents a rotation about the $X$-axis of the first qubit in a register, controlled on the second qubit, and with an angle given by the fourth parameter in a sequential model:</span></span>

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a><span data-ttu-id="6cd07-117">備註</span><span class="sxs-lookup"><span data-stu-id="6cd07-117">Remarks</span></span>

<span data-ttu-id="6cd07-118">您可以設定 `ControlIndices` 為空的索引陣列來表示無法控制的旋轉 `new Int[0]` 。</span><span class="sxs-lookup"><span data-stu-id="6cd07-118">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>