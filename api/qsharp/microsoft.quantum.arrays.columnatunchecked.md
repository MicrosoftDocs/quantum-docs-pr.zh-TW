---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 4f4631bb49f769816a3df772f7b2f346c8ccfc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842869"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="f1354-102">ColumnAtUnchecked 函式</span><span class="sxs-lookup"><span data-stu-id="f1354-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="f1354-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f1354-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f1354-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1354-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1354-105">此函數不會檢查矩陣圖形</span><span class="sxs-lookup"><span data-stu-id="f1354-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="f1354-106">描述</span><span class="sxs-lookup"><span data-stu-id="f1354-106">Description</span></span>

<span data-ttu-id="f1354-107">此函數可用於其他多維度函式中，這些函數已經檢查輸入矩陣是否有有效的矩形圖形。</span><span class="sxs-lookup"><span data-stu-id="f1354-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="f1354-108">輸入</span><span class="sxs-lookup"><span data-stu-id="f1354-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="f1354-109">資料行： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1354-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="f1354-110">矩陣： t [] []</span><span class="sxs-lookup"><span data-stu-id="f1354-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="f1354-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="f1354-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f1354-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="f1354-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f1354-113">不要</span><span class="sxs-lookup"><span data-stu-id="f1354-113">'T</span></span>

