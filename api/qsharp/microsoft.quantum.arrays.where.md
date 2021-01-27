---
uid: Microsoft.Quantum.Arrays.Where
title: Where 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842212"
---
# <a name="where-function"></a><span data-ttu-id="c9608-102">Where 函數</span><span class="sxs-lookup"><span data-stu-id="c9608-102">Where function</span></span>

<span data-ttu-id="c9608-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c9608-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c9608-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9608-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9608-105">假設有述詞和陣列，則會傳回該陣列的索引，其述詞為 true。</span><span class="sxs-lookup"><span data-stu-id="c9608-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="c9608-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c9608-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="c9608-107">述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c9608-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c9608-108">從 `'T` 到布林值的函式，用來篩選元素。</span><span class="sxs-lookup"><span data-stu-id="c9608-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="c9608-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="c9608-109">array : 'T[]</span></span>

<span data-ttu-id="c9608-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="c9608-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="c9608-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c9608-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c9608-112">索引的陣列，其中 `predicate` 為 true。</span><span class="sxs-lookup"><span data-stu-id="c9608-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c9608-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="c9608-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c9608-114">不要</span><span class="sxs-lookup"><span data-stu-id="c9608-114">'T</span></span>

<span data-ttu-id="c9608-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="c9608-115">The type of `array` elements.</span></span>