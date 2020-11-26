---
uid: Microsoft.Quantum.Arrays.Swapped
title: 交換函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 173fb32b5a41ce054f19548a7fcca18c11c4c4cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220122"
---
# <a name="swapped-function"></a><span data-ttu-id="90e3c-102">交換函數</span><span class="sxs-lookup"><span data-stu-id="90e3c-102">Swapped function</span></span>

<span data-ttu-id="90e3c-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="90e3c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="90e3c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90e3c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90e3c-105">針對陣列中的兩個元素套用交換。</span><span class="sxs-lookup"><span data-stu-id="90e3c-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="90e3c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="90e3c-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="90e3c-107">firstIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90e3c-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90e3c-108">要交換之第一個元素的索引。</span><span class="sxs-lookup"><span data-stu-id="90e3c-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="90e3c-109">secondIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90e3c-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90e3c-110">要交換的第二個元素的索引。</span><span class="sxs-lookup"><span data-stu-id="90e3c-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="90e3c-111">arr： t []</span><span class="sxs-lookup"><span data-stu-id="90e3c-111">arr : 'T[]</span></span>

<span data-ttu-id="90e3c-112">具有要交換之元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="90e3c-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="90e3c-113">Output： t []</span><span class="sxs-lookup"><span data-stu-id="90e3c-113">Output : 'T[]</span></span>

<span data-ttu-id="90e3c-114">套用了就地交換的陣列。</span><span class="sxs-lookup"><span data-stu-id="90e3c-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="90e3c-115">範例</span><span class="sxs-lookup"><span data-stu-id="90e3c-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="90e3c-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="90e3c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="90e3c-117">不要</span><span class="sxs-lookup"><span data-stu-id="90e3c-117">'T</span></span>

