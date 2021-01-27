---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: a3658bbf62068c9eea2d9b763cbff5596f426135
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854983"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="84d20-102">LocalRotationsLayer 函式</span><span class="sxs-lookup"><span data-stu-id="84d20-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="84d20-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="84d20-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="84d20-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="84d20-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="84d20-105">傳回未受控制的 (單一量子位) 旋轉的陣列，在指定的軸上，暫存器中的每個量子位都會有一次旋轉，並以相異模型參數參數化。</span><span class="sxs-lookup"><span data-stu-id="84d20-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="84d20-106">輸入</span><span class="sxs-lookup"><span data-stu-id="84d20-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="84d20-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="84d20-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="84d20-108">給定層處理的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="84d20-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="84d20-109">軸： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="84d20-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="84d20-110">給定圖層中每個旋轉的旋轉軸。</span><span class="sxs-lookup"><span data-stu-id="84d20-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="84d20-111">輸出： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="84d20-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="84d20-112">特定軸的受控制旋轉陣列，每個量子位都有一個 `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="84d20-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>