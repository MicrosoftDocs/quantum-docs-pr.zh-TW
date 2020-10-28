---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698935"
---
# <a name="operationpowa-function"></a><span data-ttu-id="a2cb0-102">OperationPowA 函式</span><span class="sxs-lookup"><span data-stu-id="a2cb0-102">OperationPowA function</span></span>

<span data-ttu-id="a2cb0-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a2cb0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a2cb0-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2cb0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2cb0-105">對電源引發運算。</span><span class="sxs-lookup"><span data-stu-id="a2cb0-105">Raises an operation to a power.</span></span>
<span data-ttu-id="a2cb0-106">修飾詞 `A` 表示作業 adjointable。</span><span class="sxs-lookup"><span data-stu-id="a2cb0-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="a2cb0-107">亦即，假設 $U $ 的作業代表閘道，則會傳回新的作業 $U ^ m $ 表示 power $m $。</span><span class="sxs-lookup"><span data-stu-id="a2cb0-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="a2cb0-108">輸入</span><span class="sxs-lookup"><span data-stu-id="a2cb0-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="a2cb0-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="a2cb0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a2cb0-110">作業 $U $ 代表要重複的閘道。</span><span class="sxs-lookup"><span data-stu-id="a2cb0-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="a2cb0-111">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a2cb0-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a2cb0-112">要重複 $U $ 的次數。</span><span class="sxs-lookup"><span data-stu-id="a2cb0-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="a2cb0-113">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="a2cb0-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a2cb0-114">代表 $U ^ m $ 的新作業，其中 $m = \texttt{power} $。</span><span class="sxs-lookup"><span data-stu-id="a2cb0-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a2cb0-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="a2cb0-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a2cb0-116">不要</span><span class="sxs-lookup"><span data-stu-id="a2cb0-116">'T</span></span>

<span data-ttu-id="a2cb0-117">要支援之作業的型別。</span><span class="sxs-lookup"><span data-stu-id="a2cb0-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2cb0-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a2cb0-118">See Also</span></span>

- [<span data-ttu-id="a2cb0-119">Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="a2cb0-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)