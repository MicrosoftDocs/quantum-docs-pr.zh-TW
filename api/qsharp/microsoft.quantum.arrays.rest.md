---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845484"
---
# <a name="rest-function"></a><span data-ttu-id="d5ee6-102">Rest 函數</span><span class="sxs-lookup"><span data-stu-id="d5ee6-102">Rest function</span></span>

<span data-ttu-id="d5ee6-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d5ee6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d5ee6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d5ee6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d5ee6-105">建立等於輸入陣列的陣列，但會卸載第一個陣列元素。</span><span class="sxs-lookup"><span data-stu-id="d5ee6-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d5ee6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d5ee6-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="d5ee6-107">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="d5ee6-107">array : 'T[]</span></span>

<span data-ttu-id="d5ee6-108">第二個元素到最後一個元素的陣列，其構成輸出陣列。</span><span class="sxs-lookup"><span data-stu-id="d5ee6-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="d5ee6-109">Output： t []</span><span class="sxs-lookup"><span data-stu-id="d5ee6-109">Output : 'T[]</span></span>

<span data-ttu-id="d5ee6-110">包含元素的陣列 `array[1..Length(array) - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="d5ee6-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d5ee6-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="d5ee6-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d5ee6-112">不要</span><span class="sxs-lookup"><span data-stu-id="d5ee6-112">'T</span></span>

<span data-ttu-id="d5ee6-113">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="d5ee6-113">The type of the array elements.</span></span>