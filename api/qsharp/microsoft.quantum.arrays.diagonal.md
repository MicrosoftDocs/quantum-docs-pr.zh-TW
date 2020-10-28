---
uid: Microsoft.Quantum.Arrays.Diagonal
title: 對角函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699507"
---
# <a name="diagonal-function"></a><span data-ttu-id="9f3ef-102">對角函數</span><span class="sxs-lookup"><span data-stu-id="9f3ef-102">Diagonal function</span></span>

<span data-ttu-id="9f3ef-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9f3ef-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9f3ef-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9f3ef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9f3ef-105">傳回二維陣列的對角線元素陣列</span><span class="sxs-lookup"><span data-stu-id="9f3ef-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="9f3ef-106">描述</span><span class="sxs-lookup"><span data-stu-id="9f3ef-106">Description</span></span>

<span data-ttu-id="9f3ef-107">如果二維陣列沒有方形圖形，則會傳回資料列和資料行數目最小值的對角線。</span><span class="sxs-lookup"><span data-stu-id="9f3ef-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="9f3ef-108">輸入</span><span class="sxs-lookup"><span data-stu-id="9f3ef-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="9f3ef-109">矩陣： t [] []</span><span class="sxs-lookup"><span data-stu-id="9f3ef-109">matrix : 'T[][]</span></span>

<span data-ttu-id="9f3ef-110">以資料列順序排列的二維矩陣</span><span class="sxs-lookup"><span data-stu-id="9f3ef-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="9f3ef-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="9f3ef-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9f3ef-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="9f3ef-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9f3ef-113">不要</span><span class="sxs-lookup"><span data-stu-id="9f3ef-113">'T</span></span>

<span data-ttu-id="9f3ef-114">之每個專案的型別 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="9f3ef-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f3ef-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9f3ef-115">See Also</span></span>

- [<span data-ttu-id="9f3ef-116">（.......。</span><span class="sxs-lookup"><span data-stu-id="9f3ef-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)