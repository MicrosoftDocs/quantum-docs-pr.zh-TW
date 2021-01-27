---
uid: Microsoft.Quantum.Arrays.Prefixes
title: 首碼函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845518"
---
# <a name="prefixes-function"></a><span data-ttu-id="6f3ea-102">首碼函數</span><span class="sxs-lookup"><span data-stu-id="6f3ea-102">Prefixes function</span></span>

<span data-ttu-id="6f3ea-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6f3ea-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6f3ea-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f3ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f3ea-105">指定陣列時，會傳回其所有前置詞。</span><span class="sxs-lookup"><span data-stu-id="6f3ea-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="6f3ea-106">描述</span><span class="sxs-lookup"><span data-stu-id="6f3ea-106">Description</span></span>

<span data-ttu-id="6f3ea-107">傳回所有前置詞的陣列，開頭為只有第一個元素才是完整陣列的陣列。</span><span class="sxs-lookup"><span data-stu-id="6f3ea-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="6f3ea-108">輸入</span><span class="sxs-lookup"><span data-stu-id="6f3ea-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="6f3ea-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="6f3ea-109">array : 'T[]</span></span>

<span data-ttu-id="6f3ea-110">元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="6f3ea-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="6f3ea-111">Output： t [] []</span><span class="sxs-lookup"><span data-stu-id="6f3ea-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6f3ea-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="6f3ea-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6f3ea-113">不要</span><span class="sxs-lookup"><span data-stu-id="6f3ea-113">'T</span></span>

<span data-ttu-id="6f3ea-114">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="6f3ea-114">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="6f3ea-115">範例</span><span class="sxs-lookup"><span data-stu-id="6f3ea-115">Example</span></span>

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```