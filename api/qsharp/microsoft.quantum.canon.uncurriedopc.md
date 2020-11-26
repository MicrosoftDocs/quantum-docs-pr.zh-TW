---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 35be5425fcd76eae9e0a6fde6a689a5db00da52f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204584"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="31158-102">UncurriedOpC 函式</span><span class="sxs-lookup"><span data-stu-id="31158-102">UncurriedOpC function</span></span>

<span data-ttu-id="31158-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="31158-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="31158-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31158-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="31158-105">假設有一個會傳回作業的函式，會傳回新的作業，它會將這兩個輸入視為一個元組。</span><span class="sxs-lookup"><span data-stu-id="31158-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="31158-106">修飾詞 `C` 表示作業可控制。</span><span class="sxs-lookup"><span data-stu-id="31158-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="31158-107">輸入</span><span class="sxs-lookup"><span data-stu-id="31158-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="31158-108">curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為 Ctl</span><span class="sxs-lookup"><span data-stu-id="31158-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="31158-109">傳回作業的函數。</span><span class="sxs-lookup"><span data-stu-id="31158-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="31158-110">輸出： ( t，' U) => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="31158-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="31158-111">`op`相當於的新作業 `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="31158-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="31158-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="31158-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="31158-113">不要</span><span class="sxs-lookup"><span data-stu-id="31158-113">'T</span></span>

<span data-ttu-id="31158-114">局部擴充函數的第一個引數類型。</span><span class="sxs-lookup"><span data-stu-id="31158-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="31158-115">' U</span><span class="sxs-lookup"><span data-stu-id="31158-115">'U</span></span>

<span data-ttu-id="31158-116">局部擴充函數的第二個引數類型。</span><span class="sxs-lookup"><span data-stu-id="31158-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="31158-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="31158-117">See Also</span></span>

- [<span data-ttu-id="31158-118">Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="31158-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)