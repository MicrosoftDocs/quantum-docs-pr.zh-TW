---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206930"
---
# <a name="fst-function"></a><span data-ttu-id="1645d-102">Fst 函式</span><span class="sxs-lookup"><span data-stu-id="1645d-102">Fst function</span></span>

<span data-ttu-id="1645d-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1645d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1645d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1645d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1645d-105">如果指定了配對，會傳回其第一個元素。</span><span class="sxs-lookup"><span data-stu-id="1645d-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="1645d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1645d-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="1645d-107">配對： ( t，' U) </span><span class="sxs-lookup"><span data-stu-id="1645d-107">pair : ('T,'U)</span></span>

<span data-ttu-id="1645d-108">具有兩個元素的元組。</span><span class="sxs-lookup"><span data-stu-id="1645d-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="1645d-109">輸出： t</span><span class="sxs-lookup"><span data-stu-id="1645d-109">Output : 'T</span></span>

<span data-ttu-id="1645d-110">`pair` 的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="1645d-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1645d-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="1645d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1645d-112">不要</span><span class="sxs-lookup"><span data-stu-id="1645d-112">'T</span></span>

<span data-ttu-id="1645d-113">配對第一個成員的類型。</span><span class="sxs-lookup"><span data-stu-id="1645d-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="1645d-114">' U</span><span class="sxs-lookup"><span data-stu-id="1645d-114">'U</span></span>

<span data-ttu-id="1645d-115">配對第二個成員的類型。</span><span class="sxs-lookup"><span data-stu-id="1645d-115">The type of the pair's second member.</span></span>