---
uid: Microsoft.Quantum.Arrays.Swapped
title: 交換函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850957"
---
# <a name="swapped-function"></a><span data-ttu-id="e556d-102">交換函數</span><span class="sxs-lookup"><span data-stu-id="e556d-102">Swapped function</span></span>

<span data-ttu-id="e556d-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e556d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e556d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e556d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e556d-105">針對陣列中的兩個元素套用交換。</span><span class="sxs-lookup"><span data-stu-id="e556d-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e556d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e556d-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="e556d-107">firstIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e556d-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e556d-108">要交換之第一個元素的索引。</span><span class="sxs-lookup"><span data-stu-id="e556d-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="e556d-109">secondIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e556d-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e556d-110">要交換的第二個元素的索引。</span><span class="sxs-lookup"><span data-stu-id="e556d-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="e556d-111">arr： t []</span><span class="sxs-lookup"><span data-stu-id="e556d-111">arr : 'T[]</span></span>

<span data-ttu-id="e556d-112">具有要交換之元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="e556d-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="e556d-113">Output： t []</span><span class="sxs-lookup"><span data-stu-id="e556d-113">Output : 'T[]</span></span>

<span data-ttu-id="e556d-114">套用了就地交換的陣列。</span><span class="sxs-lookup"><span data-stu-id="e556d-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="e556d-115">範例</span><span class="sxs-lookup"><span data-stu-id="e556d-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="e556d-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="e556d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e556d-117">不要</span><span class="sxs-lookup"><span data-stu-id="e556d-117">'T</span></span>

