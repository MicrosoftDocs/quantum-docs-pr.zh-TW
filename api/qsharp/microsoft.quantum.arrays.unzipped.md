---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 解壓縮的函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845374"
---
# <a name="unzipped-function"></a><span data-ttu-id="d4228-102">解壓縮的函式</span><span class="sxs-lookup"><span data-stu-id="d4228-102">Unzipped function</span></span>

<span data-ttu-id="d4228-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d4228-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d4228-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4228-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4228-105">假設有2個元組的陣列，會傳回兩個數組的元組，每個陣列都包含輸入陣列的元組的元素。</span><span class="sxs-lookup"><span data-stu-id="d4228-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="d4228-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d4228-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="d4228-107">arr： ( t，' U) []</span><span class="sxs-lookup"><span data-stu-id="d4228-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="d4228-108">包含2個元組的陣列</span><span class="sxs-lookup"><span data-stu-id="d4228-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="d4228-109">Output： ( t []，' U [] ) </span><span class="sxs-lookup"><span data-stu-id="d4228-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="d4228-110">兩個數組，第一個是包含輸入元組的所有第一個專案，第二個是包含輸入元組的所有第二個元素。</span><span class="sxs-lookup"><span data-stu-id="d4228-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d4228-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="d4228-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d4228-112">不要</span><span class="sxs-lookup"><span data-stu-id="d4228-112">'T</span></span>

<span data-ttu-id="d4228-113">每個元組中第一個元素的類型</span><span class="sxs-lookup"><span data-stu-id="d4228-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="d4228-114">' U</span><span class="sxs-lookup"><span data-stu-id="d4228-114">'U</span></span>

<span data-ttu-id="d4228-115">每個元組中第二個元素的類型</span><span class="sxs-lookup"><span data-stu-id="d4228-115">The type of the second element in each tuple</span></span>

## <a name="example"></a><span data-ttu-id="d4228-116">範例</span><span class="sxs-lookup"><span data-stu-id="d4228-116">Example</span></span>

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a><span data-ttu-id="d4228-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d4228-117">See Also</span></span>

- [<span data-ttu-id="d4228-118">Microsoft.Quantum.Arrays.Ziped</span><span class="sxs-lookup"><span data-stu-id="d4228-118">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)