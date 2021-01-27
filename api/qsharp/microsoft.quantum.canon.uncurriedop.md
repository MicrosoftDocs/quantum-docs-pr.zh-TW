---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: d707b52bb17f4dea795fa4ff824c785e506b8b20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851998"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="0bbc8-102">UncurriedOp 函式</span><span class="sxs-lookup"><span data-stu-id="0bbc8-102">UncurriedOp function</span></span>

<span data-ttu-id="0bbc8-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0bbc8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0bbc8-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0bbc8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0bbc8-105">假設有一個會傳回作業的函式，會傳回新的作業，它會將這兩個輸入視為一個元組。</span><span class="sxs-lookup"><span data-stu-id="0bbc8-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="0bbc8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0bbc8-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="0bbc8-107">curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0bbc8-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0bbc8-108">傳回作業的函數。</span><span class="sxs-lookup"><span data-stu-id="0bbc8-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="0bbc8-109">輸出： ( t，' U) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0bbc8-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0bbc8-110">`op`相當於的新作業 `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="0bbc8-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0bbc8-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="0bbc8-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0bbc8-112">不要</span><span class="sxs-lookup"><span data-stu-id="0bbc8-112">'T</span></span>

<span data-ttu-id="0bbc8-113">局部調用的第一個輸入類型。</span><span class="sxs-lookup"><span data-stu-id="0bbc8-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="0bbc8-114">' U</span><span class="sxs-lookup"><span data-stu-id="0bbc8-114">'U</span></span>

<span data-ttu-id="0bbc8-115">局部調用的第二個輸入型別。</span><span class="sxs-lookup"><span data-stu-id="0bbc8-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bbc8-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0bbc8-116">See Also</span></span>

- [<span data-ttu-id="0bbc8-117">Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="0bbc8-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="0bbc8-118">Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="0bbc8-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="0bbc8-119">Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="0bbc8-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)