---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 6c1917d6f1ee69cb29fed1ab173106af1e206533
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216620"
---
# <a name="curriedop-function"></a><span data-ttu-id="77359-102">CurriedOp 函式</span><span class="sxs-lookup"><span data-stu-id="77359-102">CurriedOp function</span></span>

<span data-ttu-id="77359-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="77359-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="77359-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="77359-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="77359-105">傳回兩個輸入之作業的局部擴充版本。</span><span class="sxs-lookup"><span data-stu-id="77359-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="77359-106">亦即，假設有兩個輸入的作業，此函式會將 Curry 的 isomorphism $f (x，y) \equiv f (x) # B4 y) $ 傳回一個輸入的作業，以傳回一個輸入的運算。</span><span class="sxs-lookup"><span data-stu-id="77359-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="77359-107">輸入</span><span class="sxs-lookup"><span data-stu-id="77359-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="77359-108">op： ( t，' U) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77359-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="77359-109">其輸入為成對的作業。</span><span class="sxs-lookup"><span data-stu-id="77359-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="77359-110">輸出： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77359-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="77359-111">接受一組第一個專案的作業，並傳回可接受做為其輸入的作業，該作業會將原始作業的輸入的第二個元素做為其輸入。</span><span class="sxs-lookup"><span data-stu-id="77359-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="77359-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="77359-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="77359-113">不要</span><span class="sxs-lookup"><span data-stu-id="77359-113">'T</span></span>

<span data-ttu-id="77359-114">成對定義之函式的第一個元件型別。</span><span class="sxs-lookup"><span data-stu-id="77359-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="77359-115">' U</span><span class="sxs-lookup"><span data-stu-id="77359-115">'U</span></span>

<span data-ttu-id="77359-116">成對定義之函式的第二個元件類型。</span><span class="sxs-lookup"><span data-stu-id="77359-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="77359-117">備註</span><span class="sxs-lookup"><span data-stu-id="77359-117">Remarks</span></span>

<span data-ttu-id="77359-118">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="77359-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```