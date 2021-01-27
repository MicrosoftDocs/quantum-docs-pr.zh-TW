---
uid: Microsoft.Quantum.Arrays.Diagonal
title: 對角函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842834"
---
# <a name="diagonal-function"></a><span data-ttu-id="80ca2-102">對角函數</span><span class="sxs-lookup"><span data-stu-id="80ca2-102">Diagonal function</span></span>

<span data-ttu-id="80ca2-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="80ca2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="80ca2-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80ca2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80ca2-105">傳回二維陣列的對角線元素陣列</span><span class="sxs-lookup"><span data-stu-id="80ca2-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="80ca2-106">描述</span><span class="sxs-lookup"><span data-stu-id="80ca2-106">Description</span></span>

<span data-ttu-id="80ca2-107">如果二維陣列沒有方形圖形，則會傳回資料列和資料行數目最小值的對角線。</span><span class="sxs-lookup"><span data-stu-id="80ca2-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="80ca2-108">輸入</span><span class="sxs-lookup"><span data-stu-id="80ca2-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="80ca2-109">矩陣： t [] []</span><span class="sxs-lookup"><span data-stu-id="80ca2-109">matrix : 'T[][]</span></span>

<span data-ttu-id="80ca2-110">以資料列順序排列的二維矩陣</span><span class="sxs-lookup"><span data-stu-id="80ca2-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="80ca2-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="80ca2-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="80ca2-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="80ca2-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="80ca2-113">不要</span><span class="sxs-lookup"><span data-stu-id="80ca2-113">'T</span></span>

<span data-ttu-id="80ca2-114">之每個專案的型別 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="80ca2-114">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="80ca2-115">範例</span><span class="sxs-lookup"><span data-stu-id="80ca2-115">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a><span data-ttu-id="80ca2-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="80ca2-116">See Also</span></span>

- [<span data-ttu-id="80ca2-117">（.......。</span><span class="sxs-lookup"><span data-stu-id="80ca2-117">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)