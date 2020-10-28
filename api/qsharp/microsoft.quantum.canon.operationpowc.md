---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698927"
---
# <a name="operationpowc-function"></a><span data-ttu-id="74c45-102">OperationPowC 函式</span><span class="sxs-lookup"><span data-stu-id="74c45-102">OperationPowC function</span></span>

<span data-ttu-id="74c45-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="74c45-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="74c45-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="74c45-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="74c45-105">對電源引發運算。</span><span class="sxs-lookup"><span data-stu-id="74c45-105">Raises an operation to a power.</span></span>
<span data-ttu-id="74c45-106">修飾詞 `C` 表示作業可控制。</span><span class="sxs-lookup"><span data-stu-id="74c45-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="74c45-107">亦即，假設 $U $ 的作業代表閘道，則會傳回新的作業 $U ^ m $ 表示 power $m $。</span><span class="sxs-lookup"><span data-stu-id="74c45-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="74c45-108">輸入</span><span class="sxs-lookup"><span data-stu-id="74c45-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="74c45-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="74c45-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="74c45-110">作業 $U $ 代表要重複的閘道。</span><span class="sxs-lookup"><span data-stu-id="74c45-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="74c45-111">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="74c45-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="74c45-112">要重複 $U $ 的次數。</span><span class="sxs-lookup"><span data-stu-id="74c45-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="74c45-113">Output： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="74c45-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="74c45-114">代表 $U ^ m $ 的新作業，其中 $m = \texttt{power} $。</span><span class="sxs-lookup"><span data-stu-id="74c45-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="74c45-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="74c45-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="74c45-116">不要</span><span class="sxs-lookup"><span data-stu-id="74c45-116">'T</span></span>

<span data-ttu-id="74c45-117">要支援之作業的型別。</span><span class="sxs-lookup"><span data-stu-id="74c45-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="74c45-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="74c45-118">See Also</span></span>

- [<span data-ttu-id="74c45-119">Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="74c45-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)