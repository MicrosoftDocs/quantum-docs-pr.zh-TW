---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698794"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="2a9df-102">UncurriedOpA 函式</span><span class="sxs-lookup"><span data-stu-id="2a9df-102">UncurriedOpA function</span></span>

<span data-ttu-id="2a9df-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2a9df-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2a9df-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a9df-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a9df-105">假設有一個會傳回作業的函式，會傳回新的作業，它會將這兩個輸入視為一個元組。</span><span class="sxs-lookup"><span data-stu-id="2a9df-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="2a9df-106">修飾詞 `A` 表示作業已 adjointable。</span><span class="sxs-lookup"><span data-stu-id="2a9df-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="2a9df-107">輸入</span><span class="sxs-lookup"><span data-stu-id="2a9df-107">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="2a9df-108">curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="2a9df-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2a9df-109">傳回作業的函數。</span><span class="sxs-lookup"><span data-stu-id="2a9df-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-adj"></a><span data-ttu-id="2a9df-110">輸出： ( t，' U) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="2a9df-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2a9df-111">`op`相當於的新作業 `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="2a9df-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2a9df-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="2a9df-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2a9df-113">不要</span><span class="sxs-lookup"><span data-stu-id="2a9df-113">'T</span></span>

<span data-ttu-id="2a9df-114">局部擴充函數的第一個引數類型。</span><span class="sxs-lookup"><span data-stu-id="2a9df-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="2a9df-115">' U</span><span class="sxs-lookup"><span data-stu-id="2a9df-115">'U</span></span>

<span data-ttu-id="2a9df-116">局部擴充函數的第二個引數類型。</span><span class="sxs-lookup"><span data-stu-id="2a9df-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a9df-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2a9df-117">See Also</span></span>

- [<span data-ttu-id="2a9df-118">Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="2a9df-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)