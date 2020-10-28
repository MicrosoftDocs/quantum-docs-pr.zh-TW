---
uid: Microsoft.Quantum.Arrays.Padded
title: 填補的函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699440"
---
# <a name="padded-function"></a><span data-ttu-id="dd839-102">填補的函式</span><span class="sxs-lookup"><span data-stu-id="dd839-102">Padded function</span></span>

<span data-ttu-id="dd839-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dd839-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dd839-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dd839-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dd839-105">傳回以指定的值填補的陣列（最多指定長度）。</span><span class="sxs-lookup"><span data-stu-id="dd839-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="dd839-106">輸入</span><span class="sxs-lookup"><span data-stu-id="dd839-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="dd839-107">nElementsTotal： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd839-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd839-108">填補陣列的長度。</span><span class="sxs-lookup"><span data-stu-id="dd839-108">The length of the padded array.</span></span> <span data-ttu-id="dd839-109">如果這是正面的， `inputArray` 則會在標頭填補。</span><span class="sxs-lookup"><span data-stu-id="dd839-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="dd839-110">如果是負數， `inputArray` 則會在結尾填補。</span><span class="sxs-lookup"><span data-stu-id="dd839-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="dd839-111">defaultElement： t</span><span class="sxs-lookup"><span data-stu-id="dd839-111">defaultElement : 'T</span></span>

<span data-ttu-id="dd839-112">要用於填補元素的預設值。</span><span class="sxs-lookup"><span data-stu-id="dd839-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="dd839-113">inputArray： t []</span><span class="sxs-lookup"><span data-stu-id="dd839-113">inputArray : 'T[]</span></span>

<span data-ttu-id="dd839-114">其值位於輸出陣列開頭的陣列。</span><span class="sxs-lookup"><span data-stu-id="dd839-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="dd839-115">Output： t []</span><span class="sxs-lookup"><span data-stu-id="dd839-115">Output : 'T[]</span></span>

<span data-ttu-id="dd839-116">陣列，該陣列 `output` 是 `inputArray` 以 s 為開頭且 `defaultElement` `output` 長度為的。 `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="dd839-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dd839-117">類型參數</span><span class="sxs-lookup"><span data-stu-id="dd839-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dd839-118">不要</span><span class="sxs-lookup"><span data-stu-id="dd839-118">'T</span></span>

<span data-ttu-id="dd839-119">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="dd839-119">The type of the array elements.</span></span>