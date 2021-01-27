---
uid: Microsoft.Quantum.Canon.Compose
title: 撰寫函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840913"
---
# <a name="compose-function"></a><span data-ttu-id="c10b1-102">撰寫函數</span><span class="sxs-lookup"><span data-stu-id="c10b1-102">Compose function</span></span>

<span data-ttu-id="c10b1-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c10b1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c10b1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c10b1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c10b1-105">傳回兩個函數的組合。</span><span class="sxs-lookup"><span data-stu-id="c10b1-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="c10b1-106">描述</span><span class="sxs-lookup"><span data-stu-id="c10b1-106">Description</span></span>

<span data-ttu-id="c10b1-107">假設有兩個函數 $f $ 和 $g $，則會傳回代表 $f \circ g $ 的新函式。</span><span class="sxs-lookup"><span data-stu-id="c10b1-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="c10b1-108">輸入</span><span class="sxs-lookup"><span data-stu-id="c10b1-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="c10b1-109">外部： ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="c10b1-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="c10b1-110">要套用的第二個函數。</span><span class="sxs-lookup"><span data-stu-id="c10b1-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="c10b1-111">內部： t-> ' U</span><span class="sxs-lookup"><span data-stu-id="c10b1-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="c10b1-112">要套用的第一個函數。</span><span class="sxs-lookup"><span data-stu-id="c10b1-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="c10b1-113">輸出： t-> ' V</span><span class="sxs-lookup"><span data-stu-id="c10b1-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="c10b1-114">新的函式 $h $，用於所有輸入 $x $、$f (g (x) # A3 = h (x) $。</span><span class="sxs-lookup"><span data-stu-id="c10b1-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c10b1-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="c10b1-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c10b1-116">不要</span><span class="sxs-lookup"><span data-stu-id="c10b1-116">'T</span></span>

<span data-ttu-id="c10b1-117">要套用之第一個函數的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="c10b1-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="c10b1-118">' U</span><span class="sxs-lookup"><span data-stu-id="c10b1-118">'U</span></span>

<span data-ttu-id="c10b1-119">要套用之第一個函式的輸出類型，以及要套用之第二個函式的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="c10b1-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="c10b1-120">' V</span><span class="sxs-lookup"><span data-stu-id="c10b1-120">'V</span></span>

<span data-ttu-id="c10b1-121">要套用之第二個函數的輸出類型。</span><span class="sxs-lookup"><span data-stu-id="c10b1-121">The output type of the second function to be applied.</span></span>