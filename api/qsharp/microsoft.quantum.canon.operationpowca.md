---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 338c40f8eb9d6f1782989f2a91c86df561d480bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852314"
---
# <a name="operationpowca-function"></a><span data-ttu-id="d4a15-102">OperationPowCA 函式</span><span class="sxs-lookup"><span data-stu-id="d4a15-102">OperationPowCA function</span></span>

<span data-ttu-id="d4a15-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d4a15-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d4a15-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4a15-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4a15-105">對電源引發運算。</span><span class="sxs-lookup"><span data-stu-id="d4a15-105">Raises an operation to a power.</span></span>
<span data-ttu-id="d4a15-106">修飾詞 `A` 表示作業可控制且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="d4a15-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="d4a15-107">亦即，假設 $U $ 的作業代表閘道，則會傳回新的作業 $U ^ m $ 表示 power $m $。</span><span class="sxs-lookup"><span data-stu-id="d4a15-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="d4a15-108">輸入</span><span class="sxs-lookup"><span data-stu-id="d4a15-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="d4a15-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d4a15-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d4a15-110">作業 $U $ 代表要重複的閘道。</span><span class="sxs-lookup"><span data-stu-id="d4a15-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="d4a15-111">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4a15-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4a15-112">要重複 $U $ 的次數。</span><span class="sxs-lookup"><span data-stu-id="d4a15-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="d4a15-113">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d4a15-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d4a15-114">代表 $U ^ m $ 的新作業，其中 $m = \texttt{power} $。</span><span class="sxs-lookup"><span data-stu-id="d4a15-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d4a15-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="d4a15-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d4a15-116">不要</span><span class="sxs-lookup"><span data-stu-id="d4a15-116">'T</span></span>

<span data-ttu-id="d4a15-117">要支援之作業的型別。</span><span class="sxs-lookup"><span data-stu-id="d4a15-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4a15-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d4a15-118">See Also</span></span>

- [<span data-ttu-id="d4a15-119">Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="d4a15-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)