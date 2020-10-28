---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 3fe4aa739c5e15199401aecb76ef551e52f6dcff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698126"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="7f917-102">AssertQubitWithinTolerance 操作</span><span class="sxs-lookup"><span data-stu-id="7f917-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="7f917-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7f917-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7f917-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7f917-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7f917-105">判斷提示量子位 `q` 是在預期的 Pauli Z 運算子 eigenstate 中，直到指定的容錯。</span><span class="sxs-lookup"><span data-stu-id="7f917-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="7f917-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7f917-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="7f917-107">預期： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="7f917-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="7f917-108">量子位預期在哪一個狀態： `Zero` 或 `One` 。</span><span class="sxs-lookup"><span data-stu-id="7f917-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="7f917-109">問： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7f917-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7f917-110">已判斷提示其狀態的量子位。</span><span class="sxs-lookup"><span data-stu-id="7f917-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="7f917-111">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7f917-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7f917-112">量子位的測量機率傳回預期結果的容錯。</span><span class="sxs-lookup"><span data-stu-id="7f917-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7f917-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7f917-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7f917-114">備註</span><span class="sxs-lookup"><span data-stu-id="7f917-114">Remarks</span></span>

<span data-ttu-id="7f917-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 允許判斷提示任意量子位狀態，而不只是 $Z $ eigenstates。</span><span class="sxs-lookup"><span data-stu-id="7f917-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f917-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7f917-116">See Also</span></span>

- [<span data-ttu-id="7f917-117">AssertQubitIsInStateWithinTolerance。</span><span class="sxs-lookup"><span data-stu-id="7f917-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)