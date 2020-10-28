---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698790"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="6ef89-102">UncurriedOpCA 函式</span><span class="sxs-lookup"><span data-stu-id="6ef89-102">UncurriedOpCA function</span></span>

<span data-ttu-id="6ef89-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6ef89-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6ef89-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ef89-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ef89-105">假設有一個會傳回作業的函式，會傳回新的作業，它會將這兩個輸入視為一個元組。</span><span class="sxs-lookup"><span data-stu-id="6ef89-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="6ef89-106">修飾詞 `CA` 表示作業可控制且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="6ef89-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="6ef89-107">輸入</span><span class="sxs-lookup"><span data-stu-id="6ef89-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="6ef89-108">curriedOp： t-> ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="6ef89-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="6ef89-109">傳回作業的函數。</span><span class="sxs-lookup"><span data-stu-id="6ef89-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl--adj"></a><span data-ttu-id="6ef89-110">輸出： ( t，' U) => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="6ef89-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="6ef89-111">`op`相當於的新作業 `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="6ef89-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6ef89-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="6ef89-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6ef89-113">不要</span><span class="sxs-lookup"><span data-stu-id="6ef89-113">'T</span></span>

<span data-ttu-id="6ef89-114">局部擴充函數的第一個引數類型。</span><span class="sxs-lookup"><span data-stu-id="6ef89-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="6ef89-115">' U</span><span class="sxs-lookup"><span data-stu-id="6ef89-115">'U</span></span>

<span data-ttu-id="6ef89-116">局部擴充函數的第二個引數類型。</span><span class="sxs-lookup"><span data-stu-id="6ef89-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ef89-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6ef89-117">See Also</span></span>

- [<span data-ttu-id="6ef89-118">Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="6ef89-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)