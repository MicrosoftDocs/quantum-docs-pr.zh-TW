---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210093"
---
# <a name="columnat-function"></a><span data-ttu-id="06382-102">ColumnAt 函式</span><span class="sxs-lookup"><span data-stu-id="06382-102">ColumnAt function</span></span>

<span data-ttu-id="06382-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="06382-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="06382-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06382-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06382-105">從矩陣中解壓縮資料行。</span><span class="sxs-lookup"><span data-stu-id="06382-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="06382-106">描述</span><span class="sxs-lookup"><span data-stu-id="06382-106">Description</span></span>

<span data-ttu-id="06382-107">此函式會以資料列的順序來解壓縮矩陣中的資料行。</span><span class="sxs-lookup"><span data-stu-id="06382-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="06382-108">將資料列 corrsponds 解壓縮至第一個索引的專案存取，因此不需要進一步處理。</span><span class="sxs-lookup"><span data-stu-id="06382-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="06382-109">輸入</span><span class="sxs-lookup"><span data-stu-id="06382-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="06382-110">資料行： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="06382-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="06382-111">矩陣的資料行</span><span class="sxs-lookup"><span data-stu-id="06382-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="06382-112">矩陣： t [] []</span><span class="sxs-lookup"><span data-stu-id="06382-112">matrix : 'T[][]</span></span>

<span data-ttu-id="06382-113">以資料列順序排列的二維矩陣</span><span class="sxs-lookup"><span data-stu-id="06382-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="06382-114">Output： t []</span><span class="sxs-lookup"><span data-stu-id="06382-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="06382-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="06382-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="06382-116">不要</span><span class="sxs-lookup"><span data-stu-id="06382-116">'T</span></span>

<span data-ttu-id="06382-117">之每個專案的型別 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="06382-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="06382-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="06382-118">See Also</span></span>

- [<span data-ttu-id="06382-119">（.......。</span><span class="sxs-lookup"><span data-stu-id="06382-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="06382-120">Node.js. 對角線</span><span class="sxs-lookup"><span data-stu-id="06382-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)