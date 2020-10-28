---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699519"
---
# <a name="columnat-function"></a><span data-ttu-id="f151e-102">ColumnAt 函式</span><span class="sxs-lookup"><span data-stu-id="f151e-102">ColumnAt function</span></span>

<span data-ttu-id="f151e-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f151e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f151e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f151e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f151e-105">從矩陣中解壓縮資料行。</span><span class="sxs-lookup"><span data-stu-id="f151e-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="f151e-106">描述</span><span class="sxs-lookup"><span data-stu-id="f151e-106">Description</span></span>

<span data-ttu-id="f151e-107">此函式會以資料列的順序來解壓縮矩陣中的資料行。</span><span class="sxs-lookup"><span data-stu-id="f151e-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="f151e-108">將資料列 corrsponds 解壓縮至第一個索引的專案存取，因此不需要進一步處理。</span><span class="sxs-lookup"><span data-stu-id="f151e-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="f151e-109">輸入</span><span class="sxs-lookup"><span data-stu-id="f151e-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="f151e-110">資料行： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f151e-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f151e-111">矩陣的資料行</span><span class="sxs-lookup"><span data-stu-id="f151e-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="f151e-112">矩陣： t [] []</span><span class="sxs-lookup"><span data-stu-id="f151e-112">matrix : 'T[][]</span></span>

<span data-ttu-id="f151e-113">以資料列順序排列的二維矩陣</span><span class="sxs-lookup"><span data-stu-id="f151e-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="f151e-114">Output： t []</span><span class="sxs-lookup"><span data-stu-id="f151e-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f151e-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="f151e-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f151e-116">不要</span><span class="sxs-lookup"><span data-stu-id="f151e-116">'T</span></span>

<span data-ttu-id="f151e-117">之每個專案的型別 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="f151e-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f151e-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f151e-118">See Also</span></span>

- [<span data-ttu-id="f151e-119">（.......。</span><span class="sxs-lookup"><span data-stu-id="f151e-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="f151e-120">Node.js. 對角線</span><span class="sxs-lookup"><span data-stu-id="f151e-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)