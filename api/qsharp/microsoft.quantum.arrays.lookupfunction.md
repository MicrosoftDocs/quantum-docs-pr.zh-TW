---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699455"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="2f8c6-102">LookupFunction 函式</span><span class="sxs-lookup"><span data-stu-id="2f8c6-102">LookupFunction function</span></span>

<span data-ttu-id="2f8c6-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2f8c6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2f8c6-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f8c6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2f8c6-105">指定陣列時，會傳回傳回該陣列元素的函式。</span><span class="sxs-lookup"><span data-stu-id="2f8c6-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="2f8c6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2f8c6-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="2f8c6-107">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="2f8c6-107">array : 'T[]</span></span>

<span data-ttu-id="2f8c6-108">要表示為查閱函數的陣列。</span><span class="sxs-lookup"><span data-stu-id="2f8c6-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="2f8c6-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int) -> t</span><span class="sxs-lookup"><span data-stu-id="2f8c6-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="2f8c6-110">`f`這樣的函式 `f(idx) == f[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="2f8c6-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2f8c6-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="2f8c6-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f8c6-112">不要</span><span class="sxs-lookup"><span data-stu-id="2f8c6-112">'T</span></span>

<span data-ttu-id="2f8c6-113">陣列元素的型別，以 lookup 函數表示。</span><span class="sxs-lookup"><span data-stu-id="2f8c6-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f8c6-114">備註</span><span class="sxs-lookup"><span data-stu-id="2f8c6-114">Remarks</span></span>

<span data-ttu-id="2f8c6-115">此函式主要適用于與以函式 `Int -> 'T` 作為其引數的函式和作業交互操作。</span><span class="sxs-lookup"><span data-stu-id="2f8c6-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="2f8c6-116">這種情況很常見，例如，在產生器表示程式庫中，函式是用來避免需要在記憶體中記錄整個陣列。</span><span class="sxs-lookup"><span data-stu-id="2f8c6-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>