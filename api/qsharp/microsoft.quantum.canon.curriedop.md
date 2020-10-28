---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 13bc3e195d8a4ba26b726f96e4dc6b83da43c3e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699048"
---
# <a name="curriedop-function"></a><span data-ttu-id="40997-102">CurriedOp 函式</span><span class="sxs-lookup"><span data-stu-id="40997-102">CurriedOp function</span></span>

<span data-ttu-id="40997-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="40997-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="40997-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="40997-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="40997-105">傳回兩個輸入之作業的局部擴充版本。</span><span class="sxs-lookup"><span data-stu-id="40997-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="40997-106">亦即，假設有兩個輸入的作業，此函式會將 Curry 的 isomorphism $f (x，y) \equiv f (x) # B4 y) $ 傳回一個輸入的作業，以傳回一個輸入的運算。</span><span class="sxs-lookup"><span data-stu-id="40997-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="40997-107">輸入</span><span class="sxs-lookup"><span data-stu-id="40997-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="40997-108">op： ( t，' U) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40997-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="40997-109">其輸入為成對的作業。</span><span class="sxs-lookup"><span data-stu-id="40997-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="40997-110">輸出： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40997-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="40997-111">接受一組第一個專案的作業，並傳回可接受做為其輸入的作業，該作業會將原始作業的輸入的第二個元素做為其輸入。</span><span class="sxs-lookup"><span data-stu-id="40997-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="40997-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="40997-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="40997-113">不要</span><span class="sxs-lookup"><span data-stu-id="40997-113">'T</span></span>

<span data-ttu-id="40997-114">成對定義之函式的第一個元件型別。</span><span class="sxs-lookup"><span data-stu-id="40997-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="40997-115">' U</span><span class="sxs-lookup"><span data-stu-id="40997-115">'U</span></span>

<span data-ttu-id="40997-116">成對定義之函式的第二個元件類型。</span><span class="sxs-lookup"><span data-stu-id="40997-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="40997-117">備註</span><span class="sxs-lookup"><span data-stu-id="40997-117">Remarks</span></span>

<span data-ttu-id="40997-118">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="40997-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```