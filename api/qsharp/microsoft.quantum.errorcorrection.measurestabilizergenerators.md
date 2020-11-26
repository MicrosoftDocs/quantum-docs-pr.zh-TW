---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: 6c048c17df21d1026dc671f30d72a13ed8d8b7f5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200623"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="4163a-102">MeasureStabilizerGenerators 操作</span><span class="sxs-lookup"><span data-stu-id="4163a-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="4163a-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="4163a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="4163a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4163a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4163a-105">測量一組指定的穩定產生器群組。</span><span class="sxs-lookup"><span data-stu-id="4163a-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="4163a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="4163a-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="4163a-107">stabilizerGroup： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="4163a-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="4163a-108">Multiqubit Pauli 運算子的陣列。</span><span class="sxs-lookup"><span data-stu-id="4163a-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="4163a-109">例如， `stabilizerGroup[0]` 是單一量子位 Pauli 矩陣的清單，其 tensor 產品是一個穩定器產生器。</span><span class="sxs-lookup"><span data-stu-id="4163a-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="4163a-110">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="4163a-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="4163a-111">定義了穩定程式碼的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="4163a-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="4163a-112">小工具： ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) =>__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="4163a-112">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="4163a-113">指定如何測量 multiqubit Pauli 運算子的作業。</span><span class="sxs-lookup"><span data-stu-id="4163a-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="4163a-114">輸出： [症狀](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="4163a-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="4163a-115">度量的結果。</span><span class="sxs-lookup"><span data-stu-id="4163a-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="4163a-116">備註</span><span class="sxs-lookup"><span data-stu-id="4163a-116">Remarks</span></span>

<span data-ttu-id="4163a-117">這不會檢查指定的產生器集是否通勤。</span><span class="sxs-lookup"><span data-stu-id="4163a-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="4163a-118">如果未通勤，測量結果可能是任意的。</span><span class="sxs-lookup"><span data-stu-id="4163a-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>