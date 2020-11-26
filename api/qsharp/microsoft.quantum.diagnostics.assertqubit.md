---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 0e005230427bbd570133712679c51661e7ae6496
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202238"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="bcf93-102">AssertQubit 操作</span><span class="sxs-lookup"><span data-stu-id="bcf93-102">AssertQubit operation</span></span>

<span data-ttu-id="bcf93-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="bcf93-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="bcf93-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bcf93-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bcf93-105">判斷提示量子位 `q` 是在 Pauli Z 運算子的預期 eigenstate 中。</span><span class="sxs-lookup"><span data-stu-id="bcf93-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="bcf93-106">輸入</span><span class="sxs-lookup"><span data-stu-id="bcf93-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="bcf93-107">預期：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="bcf93-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="bcf93-108">量子位預期在哪一個狀態： `Zero` 或 `One` 。</span><span class="sxs-lookup"><span data-stu-id="bcf93-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="bcf93-109">問： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bcf93-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bcf93-110">已判斷提示其狀態的量子位。</span><span class="sxs-lookup"><span data-stu-id="bcf93-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bcf93-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bcf93-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bcf93-112">備註</span><span class="sxs-lookup"><span data-stu-id="bcf93-112">Remarks</span></span>

<span data-ttu-id="bcf93-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 允許判斷提示任意量子位狀態，而不只是 $Z $ eigenstates。</span><span class="sxs-lookup"><span data-stu-id="bcf93-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="bcf93-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bcf93-114">See Also</span></span>

- [<span data-ttu-id="bcf93-115">AssertQubitIsInStateWithinTolerance。</span><span class="sxs-lookup"><span data-stu-id="bcf93-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)