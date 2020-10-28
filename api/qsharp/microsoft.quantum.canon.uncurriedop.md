---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698799"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="a8d72-102">UncurriedOp 函式</span><span class="sxs-lookup"><span data-stu-id="a8d72-102">UncurriedOp function</span></span>

<span data-ttu-id="a8d72-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a8d72-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a8d72-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8d72-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8d72-105">假設有一個會傳回作業的函式，會傳回新的作業，它會將這兩個輸入視為一個元組。</span><span class="sxs-lookup"><span data-stu-id="a8d72-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="a8d72-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a8d72-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="a8d72-107">curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8d72-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a8d72-108">傳回作業的函數。</span><span class="sxs-lookup"><span data-stu-id="a8d72-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="a8d72-109">輸出： ( t，' U) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8d72-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a8d72-110">`op`相當於的新作業 `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="a8d72-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a8d72-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="a8d72-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a8d72-112">不要</span><span class="sxs-lookup"><span data-stu-id="a8d72-112">'T</span></span>

<span data-ttu-id="a8d72-113">局部調用的第一個輸入類型。</span><span class="sxs-lookup"><span data-stu-id="a8d72-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="a8d72-114">' U</span><span class="sxs-lookup"><span data-stu-id="a8d72-114">'U</span></span>

<span data-ttu-id="a8d72-115">局部調用的第二個輸入型別。</span><span class="sxs-lookup"><span data-stu-id="a8d72-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8d72-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a8d72-116">See Also</span></span>

- [<span data-ttu-id="a8d72-117">Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="a8d72-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="a8d72-118">Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="a8d72-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="a8d72-119">Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="a8d72-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)