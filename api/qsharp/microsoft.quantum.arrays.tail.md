---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 680562228a39263ef87ba053e6b7683412947e46
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845416"
---
# <a name="tail-function"></a><span data-ttu-id="46f7a-102">Tail 函數</span><span class="sxs-lookup"><span data-stu-id="46f7a-102">Tail function</span></span>

<span data-ttu-id="46f7a-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="46f7a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="46f7a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="46f7a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="46f7a-105">傳回陣列的最後一個元素。</span><span class="sxs-lookup"><span data-stu-id="46f7a-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="46f7a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="46f7a-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="46f7a-107">陣列： ' A []</span><span class="sxs-lookup"><span data-stu-id="46f7a-107">array : 'A[]</span></span>

<span data-ttu-id="46f7a-108">取得最後一個元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="46f7a-108">Array of which the last element is taken.</span></span> <span data-ttu-id="46f7a-109">陣列的長度至少必須為1。</span><span class="sxs-lookup"><span data-stu-id="46f7a-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="46f7a-110">輸出： ' A</span><span class="sxs-lookup"><span data-stu-id="46f7a-110">Output : 'A</span></span>

<span data-ttu-id="46f7a-111">陣列的最後一個元素。</span><span class="sxs-lookup"><span data-stu-id="46f7a-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="46f7a-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="46f7a-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="46f7a-113">' A</span><span class="sxs-lookup"><span data-stu-id="46f7a-113">'A</span></span>

<span data-ttu-id="46f7a-114">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="46f7a-114">The type of the array elements.</span></span>