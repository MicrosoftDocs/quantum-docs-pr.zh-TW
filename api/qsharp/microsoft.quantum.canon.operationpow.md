---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 9ed0d32c084f183527cac0586ad699417f51df29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852371"
---
# <a name="operationpow-function"></a><span data-ttu-id="56fb6-102">OperationPow 函式</span><span class="sxs-lookup"><span data-stu-id="56fb6-102">OperationPow function</span></span>

<span data-ttu-id="56fb6-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="56fb6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="56fb6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56fb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56fb6-105">對電源引發運算。</span><span class="sxs-lookup"><span data-stu-id="56fb6-105">Raises an operation to a power.</span></span>

<span data-ttu-id="56fb6-106">亦即，假設 $U $ 的作業代表閘道，則會傳回新的作業 $U ^ m $ 表示 power $m $。</span><span class="sxs-lookup"><span data-stu-id="56fb6-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="56fb6-107">輸入</span><span class="sxs-lookup"><span data-stu-id="56fb6-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="56fb6-108">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56fb6-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="56fb6-109">作業 $U $ 代表要重複的閘道。</span><span class="sxs-lookup"><span data-stu-id="56fb6-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="56fb6-110">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="56fb6-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="56fb6-111">要重複 $U $ 的次數。</span><span class="sxs-lookup"><span data-stu-id="56fb6-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="56fb6-112">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56fb6-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="56fb6-113">代表 $U ^ m $ 的新作業，其中 $m = \texttt{power} $。</span><span class="sxs-lookup"><span data-stu-id="56fb6-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="56fb6-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="56fb6-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="56fb6-115">不要</span><span class="sxs-lookup"><span data-stu-id="56fb6-115">'T</span></span>

<span data-ttu-id="56fb6-116">要支援之作業的型別。</span><span class="sxs-lookup"><span data-stu-id="56fb6-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="56fb6-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="56fb6-117">See Also</span></span>

- [<span data-ttu-id="56fb6-118">Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="56fb6-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="56fb6-119">Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="56fb6-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="56fb6-120">Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="56fb6-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)