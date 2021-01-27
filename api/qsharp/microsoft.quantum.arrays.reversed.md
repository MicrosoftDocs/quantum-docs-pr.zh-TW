---
uid: Microsoft.Quantum.Arrays.Reversed
title: 反轉函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845464"
---
# <a name="reversed-function"></a><span data-ttu-id="f9290-102">反轉函數</span><span class="sxs-lookup"><span data-stu-id="f9290-102">Reversed function</span></span>

<span data-ttu-id="f9290-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f9290-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f9290-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9290-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9290-105">建立陣列，其中包含與輸入陣列相同的元素，但以反向順序表示。</span><span class="sxs-lookup"><span data-stu-id="f9290-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f9290-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f9290-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="f9290-107">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="f9290-107">array : 'T[]</span></span>

<span data-ttu-id="f9290-108">要以反轉順序複製其元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="f9290-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="f9290-109">Output： t []</span><span class="sxs-lookup"><span data-stu-id="f9290-109">Output : 'T[]</span></span>

<span data-ttu-id="f9290-110">包含元素的陣列 `array[Length(array) - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="f9290-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="f9290-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="f9290-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f9290-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="f9290-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9290-113">不要</span><span class="sxs-lookup"><span data-stu-id="f9290-113">'T</span></span>

<span data-ttu-id="f9290-114">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="f9290-114">The type of the array elements.</span></span>