---
uid: Microsoft.Quantum.Arrays.Prefixes
title: 首碼函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699433"
---
# <a name="prefixes-function"></a><span data-ttu-id="e80cc-102">首碼函數</span><span class="sxs-lookup"><span data-stu-id="e80cc-102">Prefixes function</span></span>

<span data-ttu-id="e80cc-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e80cc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e80cc-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e80cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e80cc-105">指定陣列時，會傳回其所有前置詞。</span><span class="sxs-lookup"><span data-stu-id="e80cc-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="e80cc-106">描述</span><span class="sxs-lookup"><span data-stu-id="e80cc-106">Description</span></span>

<span data-ttu-id="e80cc-107">傳回所有前置詞的陣列，開頭為只有第一個元素才是完整陣列的陣列。</span><span class="sxs-lookup"><span data-stu-id="e80cc-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="e80cc-108">輸入</span><span class="sxs-lookup"><span data-stu-id="e80cc-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="e80cc-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="e80cc-109">array : 'T[]</span></span>

<span data-ttu-id="e80cc-110">元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="e80cc-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="e80cc-111">Output： t [] []</span><span class="sxs-lookup"><span data-stu-id="e80cc-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e80cc-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="e80cc-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e80cc-113">不要</span><span class="sxs-lookup"><span data-stu-id="e80cc-113">'T</span></span>

<span data-ttu-id="e80cc-114">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="e80cc-114">The type of `array` elements.</span></span>