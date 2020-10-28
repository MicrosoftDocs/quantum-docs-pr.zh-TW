---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698951"
---
# <a name="operationpow-function"></a><span data-ttu-id="6179f-102">OperationPow 函式</span><span class="sxs-lookup"><span data-stu-id="6179f-102">OperationPow function</span></span>

<span data-ttu-id="6179f-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6179f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6179f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6179f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6179f-105">對電源引發運算。</span><span class="sxs-lookup"><span data-stu-id="6179f-105">Raises an operation to a power.</span></span>

<span data-ttu-id="6179f-106">亦即，假設 $U $ 的作業代表閘道，則會傳回新的作業 $U ^ m $ 表示 power $m $。</span><span class="sxs-lookup"><span data-stu-id="6179f-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="6179f-107">輸入</span><span class="sxs-lookup"><span data-stu-id="6179f-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="6179f-108">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6179f-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6179f-109">作業 $U $ 代表要重複的閘道。</span><span class="sxs-lookup"><span data-stu-id="6179f-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="6179f-110">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6179f-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6179f-111">要重複 $U $ 的次數。</span><span class="sxs-lookup"><span data-stu-id="6179f-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="6179f-112">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6179f-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6179f-113">代表 $U ^ m $ 的新作業，其中 $m = \texttt{power} $。</span><span class="sxs-lookup"><span data-stu-id="6179f-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6179f-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="6179f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6179f-115">不要</span><span class="sxs-lookup"><span data-stu-id="6179f-115">'T</span></span>

<span data-ttu-id="6179f-116">要支援之作業的型別。</span><span class="sxs-lookup"><span data-stu-id="6179f-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="6179f-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6179f-117">See Also</span></span>

- [<span data-ttu-id="6179f-118">Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="6179f-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="6179f-119">Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="6179f-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="6179f-120">Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="6179f-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)