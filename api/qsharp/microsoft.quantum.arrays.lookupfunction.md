---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: 22b56bb7e9f03ebc5b2225efb2e6450d56022664
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845691"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="aef2b-102">LookupFunction 函式</span><span class="sxs-lookup"><span data-stu-id="aef2b-102">LookupFunction function</span></span>

<span data-ttu-id="aef2b-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="aef2b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="aef2b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aef2b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aef2b-105">指定陣列時，會傳回傳回該陣列元素的函式。</span><span class="sxs-lookup"><span data-stu-id="aef2b-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="aef2b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="aef2b-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="aef2b-107">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="aef2b-107">array : 'T[]</span></span>

<span data-ttu-id="aef2b-108">要表示為查閱函數的陣列。</span><span class="sxs-lookup"><span data-stu-id="aef2b-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="aef2b-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int) -> t</span><span class="sxs-lookup"><span data-stu-id="aef2b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="aef2b-110">`f`這樣的函式 `f(idx) == f[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="aef2b-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="aef2b-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="aef2b-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aef2b-112">不要</span><span class="sxs-lookup"><span data-stu-id="aef2b-112">'T</span></span>

<span data-ttu-id="aef2b-113">陣列元素的型別，以 lookup 函數表示。</span><span class="sxs-lookup"><span data-stu-id="aef2b-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="aef2b-114">備註</span><span class="sxs-lookup"><span data-stu-id="aef2b-114">Remarks</span></span>

<span data-ttu-id="aef2b-115">此函式主要適用于與以函式 `Int -> 'T` 作為其引數的函式和作業交互操作。</span><span class="sxs-lookup"><span data-stu-id="aef2b-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="aef2b-116">這種情況很常見，例如，在產生器表示程式庫中，函式是用來避免需要在記憶體中記錄整個陣列。</span><span class="sxs-lookup"><span data-stu-id="aef2b-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>