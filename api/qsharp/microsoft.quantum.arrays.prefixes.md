---
uid: Microsoft.Quantum.Arrays.Prefixes
title: 首碼函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220379"
---
# <a name="prefixes-function"></a><span data-ttu-id="a119c-102">首碼函數</span><span class="sxs-lookup"><span data-stu-id="a119c-102">Prefixes function</span></span>

<span data-ttu-id="a119c-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a119c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a119c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a119c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a119c-105">指定陣列時，會傳回其所有前置詞。</span><span class="sxs-lookup"><span data-stu-id="a119c-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="a119c-106">描述</span><span class="sxs-lookup"><span data-stu-id="a119c-106">Description</span></span>

<span data-ttu-id="a119c-107">傳回所有前置詞的陣列，開頭為只有第一個元素才是完整陣列的陣列。</span><span class="sxs-lookup"><span data-stu-id="a119c-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="a119c-108">輸入</span><span class="sxs-lookup"><span data-stu-id="a119c-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="a119c-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="a119c-109">array : 'T[]</span></span>

<span data-ttu-id="a119c-110">元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="a119c-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="a119c-111">Output： t [] []</span><span class="sxs-lookup"><span data-stu-id="a119c-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a119c-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="a119c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a119c-113">不要</span><span class="sxs-lookup"><span data-stu-id="a119c-113">'T</span></span>

<span data-ttu-id="a119c-114">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="a119c-114">The type of `array` elements.</span></span>