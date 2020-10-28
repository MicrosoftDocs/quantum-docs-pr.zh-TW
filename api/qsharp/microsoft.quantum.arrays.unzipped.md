---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 解壓縮的函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699408"
---
# <a name="unzipped-function"></a><span data-ttu-id="e6c80-102">解壓縮的函式</span><span class="sxs-lookup"><span data-stu-id="e6c80-102">Unzipped function</span></span>

<span data-ttu-id="e6c80-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e6c80-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e6c80-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e6c80-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e6c80-105">假設有2個元組的陣列，會傳回兩個數組的元組，每個陣列都包含輸入陣列的元組的元素。</span><span class="sxs-lookup"><span data-stu-id="e6c80-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="e6c80-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e6c80-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="e6c80-107">arr： ( t，' U) []</span><span class="sxs-lookup"><span data-stu-id="e6c80-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="e6c80-108">包含2個元組的陣列</span><span class="sxs-lookup"><span data-stu-id="e6c80-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="e6c80-109">Output： ( t []，' U [] ) </span><span class="sxs-lookup"><span data-stu-id="e6c80-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="e6c80-110">兩個數組，第一個是包含輸入元組的所有第一個專案，第二個是包含輸入元組的所有第二個元素。</span><span class="sxs-lookup"><span data-stu-id="e6c80-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e6c80-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="e6c80-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e6c80-112">不要</span><span class="sxs-lookup"><span data-stu-id="e6c80-112">'T</span></span>

<span data-ttu-id="e6c80-113">每個元組中第一個元素的類型</span><span class="sxs-lookup"><span data-stu-id="e6c80-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="e6c80-114">' U</span><span class="sxs-lookup"><span data-stu-id="e6c80-114">'U</span></span>

<span data-ttu-id="e6c80-115">每個元組中第二個元素的類型</span><span class="sxs-lookup"><span data-stu-id="e6c80-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="e6c80-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e6c80-116">See Also</span></span>

- [<span data-ttu-id="e6c80-117">Microsoft.Quantum.Arrays.Ziped</span><span class="sxs-lookup"><span data-stu-id="e6c80-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)