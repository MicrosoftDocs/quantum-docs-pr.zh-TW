---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698143"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="76264-102">AssertQubit 操作</span><span class="sxs-lookup"><span data-stu-id="76264-102">AssertQubit operation</span></span>

<span data-ttu-id="76264-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="76264-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="76264-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76264-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76264-105">判斷提示量子位 `q` 是在 Pauli Z 運算子的預期 eigenstate 中。</span><span class="sxs-lookup"><span data-stu-id="76264-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="76264-106">輸入</span><span class="sxs-lookup"><span data-stu-id="76264-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="76264-107">預期： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="76264-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="76264-108">量子位預期在哪一個狀態： `Zero` 或 `One` 。</span><span class="sxs-lookup"><span data-stu-id="76264-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="76264-109">問： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="76264-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="76264-110">已判斷提示其狀態的量子位。</span><span class="sxs-lookup"><span data-stu-id="76264-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76264-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76264-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="76264-112">備註</span><span class="sxs-lookup"><span data-stu-id="76264-112">Remarks</span></span>

<span data-ttu-id="76264-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 允許判斷提示任意量子位狀態，而不只是 $Z $ eigenstates。</span><span class="sxs-lookup"><span data-stu-id="76264-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="76264-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="76264-114">See Also</span></span>

- [<span data-ttu-id="76264-115">AssertQubitIsInStateWithinTolerance。</span><span class="sxs-lookup"><span data-stu-id="76264-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)