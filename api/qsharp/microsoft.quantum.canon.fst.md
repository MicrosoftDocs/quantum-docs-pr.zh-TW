---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840507"
---
# <a name="fst-function"></a><span data-ttu-id="6e0f7-102">Fst 函式</span><span class="sxs-lookup"><span data-stu-id="6e0f7-102">Fst function</span></span>

<span data-ttu-id="6e0f7-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6e0f7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6e0f7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e0f7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e0f7-105">如果指定了配對，會傳回其第一個元素。</span><span class="sxs-lookup"><span data-stu-id="6e0f7-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="6e0f7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6e0f7-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="6e0f7-107">配對： ( t，' U) </span><span class="sxs-lookup"><span data-stu-id="6e0f7-107">pair : ('T,'U)</span></span>

<span data-ttu-id="6e0f7-108">具有兩個元素的元組。</span><span class="sxs-lookup"><span data-stu-id="6e0f7-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="6e0f7-109">輸出： t</span><span class="sxs-lookup"><span data-stu-id="6e0f7-109">Output : 'T</span></span>

<span data-ttu-id="6e0f7-110">`pair` 的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="6e0f7-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6e0f7-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="6e0f7-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6e0f7-112">不要</span><span class="sxs-lookup"><span data-stu-id="6e0f7-112">'T</span></span>

<span data-ttu-id="6e0f7-113">配對第一個成員的類型。</span><span class="sxs-lookup"><span data-stu-id="6e0f7-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="6e0f7-114">' U</span><span class="sxs-lookup"><span data-stu-id="6e0f7-114">'U</span></span>

<span data-ttu-id="6e0f7-115">配對第二個成員的類型。</span><span class="sxs-lookup"><span data-stu-id="6e0f7-115">The type of the pair's second member.</span></span>