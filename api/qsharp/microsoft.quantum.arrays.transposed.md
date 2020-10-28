---
uid: Microsoft.Quantum.Arrays.Transposed
title: 已轉換函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699412"
---
# <a name="transposed-function"></a><span data-ttu-id="aabc1-102">已轉換函式</span><span class="sxs-lookup"><span data-stu-id="aabc1-102">Transposed function</span></span>

<span data-ttu-id="aabc1-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="aabc1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="aabc1-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aabc1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aabc1-105">傳回表示為數組陣列的矩陣的調換。</span><span class="sxs-lookup"><span data-stu-id="aabc1-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="aabc1-106">描述</span><span class="sxs-lookup"><span data-stu-id="aabc1-106">Description</span></span>

<span data-ttu-id="aabc1-107">以 $r \times c $ 矩陣的形式輸入 $r $ rows 和 $c $ columns。</span><span class="sxs-lookup"><span data-stu-id="aabc1-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="aabc1-108">矩陣是以資料列為基礎，也就是 `matrix[i][j]` 存取資料列 $i $ 和 column $j $ 的元素。</span><span class="sxs-lookup"><span data-stu-id="aabc1-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="aabc1-109">此函式會傳回 $c \times r $ matrix，這是輸入矩陣的換位。</span><span class="sxs-lookup"><span data-stu-id="aabc1-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="aabc1-110">輸入</span><span class="sxs-lookup"><span data-stu-id="aabc1-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="aabc1-111">矩陣： t [] []</span><span class="sxs-lookup"><span data-stu-id="aabc1-111">matrix : 'T[][]</span></span>

<span data-ttu-id="aabc1-112">以資料列為基礎的 $r \times c $ matrix</span><span class="sxs-lookup"><span data-stu-id="aabc1-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="aabc1-113">Output： t [] []</span><span class="sxs-lookup"><span data-stu-id="aabc1-113">Output : 'T[][]</span></span>

<span data-ttu-id="aabc1-114">已轉換 $c \times r $ matrix</span><span class="sxs-lookup"><span data-stu-id="aabc1-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="aabc1-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="aabc1-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aabc1-116">不要</span><span class="sxs-lookup"><span data-stu-id="aabc1-116">'T</span></span>

<span data-ttu-id="aabc1-117">之每個專案的型別 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="aabc1-117">The type of each element of `matrix`.</span></span>