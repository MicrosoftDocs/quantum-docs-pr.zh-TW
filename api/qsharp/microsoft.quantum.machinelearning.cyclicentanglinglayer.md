---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5d0af0a60217b69dc7eb8ece8952f2a7f0c09280
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847373"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="48dff-102">CyclicEntanglingLayer 函式</span><span class="sxs-lookup"><span data-stu-id="48dff-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="48dff-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="48dff-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="48dff-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="48dff-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="48dff-105">傳回沿著指定軸的單一控制旋轉陣列、在量子位的暫存器中排列迴圈，並以相異模型參數參數化。</span><span class="sxs-lookup"><span data-stu-id="48dff-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="48dff-106">輸入</span><span class="sxs-lookup"><span data-stu-id="48dff-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="48dff-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48dff-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48dff-108">給定層處理的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="48dff-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="48dff-109">軸： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="48dff-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="48dff-110">給定圖層中每個旋轉的旋轉軸。</span><span class="sxs-lookup"><span data-stu-id="48dff-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="48dff-111">stride： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48dff-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48dff-112">每個旋轉的目標和控制項索引之間的分隔。</span><span class="sxs-lookup"><span data-stu-id="48dff-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="48dff-113">輸出： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="48dff-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="48dff-114">兩個量子位控制的旋轉陣列，會在量子位的暫存器上配置迴圈 `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="48dff-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>

## <a name="example"></a><span data-ttu-id="48dff-115">範例</span><span class="sxs-lookup"><span data-stu-id="48dff-115">Example</span></span>

<span data-ttu-id="48dff-116">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="48dff-116">The following are equivalent:</span></span>

```qsharp
let layer = CyclicEntanglingLayer(3, PauliX, 2);
let layer = [
    ControlledRotation((0, [2]), PauliX, 0),
    ControlledRotation((1, [0]), PauliX, 1),
    ControlledRotation((2, [1]), PauliX, 2)
];
```