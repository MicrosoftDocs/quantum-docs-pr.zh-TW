---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: feb5da771ee6cb6a750fa76f9ffd8f5a3e0b5734
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840059"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="7857f-102">UncurriedOpA 函式</span><span class="sxs-lookup"><span data-stu-id="7857f-102">UncurriedOpA function</span></span>

<span data-ttu-id="7857f-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7857f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7857f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7857f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7857f-105">假設有一個會傳回作業的函式，會傳回新的作業，它會將這兩個輸入視為一個元組。</span><span class="sxs-lookup"><span data-stu-id="7857f-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="7857f-106">修飾詞 `A` 表示作業已 adjointable。</span><span class="sxs-lookup"><span data-stu-id="7857f-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="7857f-107">輸入</span><span class="sxs-lookup"><span data-stu-id="7857f-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="7857f-108">curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="7857f-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7857f-109">傳回作業的函數。</span><span class="sxs-lookup"><span data-stu-id="7857f-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="7857f-110">輸出： ( t，' U) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="7857f-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7857f-111">`op`相當於的新作業 `op(t, u)` `(curriedOp(t))(u)` 。</span><span class="sxs-lookup"><span data-stu-id="7857f-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7857f-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="7857f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7857f-113">不要</span><span class="sxs-lookup"><span data-stu-id="7857f-113">'T</span></span>

<span data-ttu-id="7857f-114">局部擴充函數的第一個引數類型。</span><span class="sxs-lookup"><span data-stu-id="7857f-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="7857f-115">' U</span><span class="sxs-lookup"><span data-stu-id="7857f-115">'U</span></span>

<span data-ttu-id="7857f-116">局部擴充函數的第二個引數類型。</span><span class="sxs-lookup"><span data-stu-id="7857f-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="7857f-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7857f-117">See Also</span></span>

- [<span data-ttu-id="7857f-118">Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="7857f-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)