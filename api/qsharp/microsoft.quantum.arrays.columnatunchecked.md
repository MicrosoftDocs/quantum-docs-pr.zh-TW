---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 06fce23bbf7142ee0e0b0ed3f2c0578676f2097b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221584"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="85130-102">ColumnAtUnchecked 函式</span><span class="sxs-lookup"><span data-stu-id="85130-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="85130-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="85130-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="85130-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85130-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85130-105">此函數不會檢查矩陣圖形</span><span class="sxs-lookup"><span data-stu-id="85130-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="85130-106">描述</span><span class="sxs-lookup"><span data-stu-id="85130-106">Description</span></span>

<span data-ttu-id="85130-107">此函數可用於其他多維度函式中，這些函數已經檢查輸入矩陣是否有有效的矩形圖形。</span><span class="sxs-lookup"><span data-stu-id="85130-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="85130-108">輸入</span><span class="sxs-lookup"><span data-stu-id="85130-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="85130-109">資料行： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="85130-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="85130-110">矩陣： t [] []</span><span class="sxs-lookup"><span data-stu-id="85130-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="85130-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="85130-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="85130-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="85130-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="85130-113">不要</span><span class="sxs-lookup"><span data-stu-id="85130-113">'T</span></span>

