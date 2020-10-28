---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699022"
---
# <a name="fst-function"></a><span data-ttu-id="76939-102">Fst 函式</span><span class="sxs-lookup"><span data-stu-id="76939-102">Fst function</span></span>

<span data-ttu-id="76939-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="76939-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="76939-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76939-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76939-105">如果指定了配對，會傳回其第一個元素。</span><span class="sxs-lookup"><span data-stu-id="76939-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="76939-106">輸入</span><span class="sxs-lookup"><span data-stu-id="76939-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="76939-107">配對： ( t，' U) </span><span class="sxs-lookup"><span data-stu-id="76939-107">pair : ('T,'U)</span></span>

<span data-ttu-id="76939-108">具有兩個元素的元組。</span><span class="sxs-lookup"><span data-stu-id="76939-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="76939-109">輸出： t</span><span class="sxs-lookup"><span data-stu-id="76939-109">Output : 'T</span></span>

<span data-ttu-id="76939-110">`pair` 的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="76939-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="76939-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="76939-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76939-112">不要</span><span class="sxs-lookup"><span data-stu-id="76939-112">'T</span></span>

<span data-ttu-id="76939-113">配對第一個成員的類型。</span><span class="sxs-lookup"><span data-stu-id="76939-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="76939-114">' U</span><span class="sxs-lookup"><span data-stu-id="76939-114">'U</span></span>

<span data-ttu-id="76939-115">配對第二個成員的類型。</span><span class="sxs-lookup"><span data-stu-id="76939-115">The type of the pair's second member.</span></span>