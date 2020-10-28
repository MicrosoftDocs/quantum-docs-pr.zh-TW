---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699429"
---
# <a name="rest-function"></a><span data-ttu-id="feb7f-102">Rest 函數</span><span class="sxs-lookup"><span data-stu-id="feb7f-102">Rest function</span></span>

<span data-ttu-id="feb7f-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="feb7f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="feb7f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="feb7f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="feb7f-105">建立等於輸入陣列的陣列，但會卸載第一個陣列元素。</span><span class="sxs-lookup"><span data-stu-id="feb7f-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="feb7f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="feb7f-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="feb7f-107">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="feb7f-107">array : 'T[]</span></span>

<span data-ttu-id="feb7f-108">第二個元素到最後一個元素的陣列，其構成輸出陣列。</span><span class="sxs-lookup"><span data-stu-id="feb7f-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="feb7f-109">Output： t []</span><span class="sxs-lookup"><span data-stu-id="feb7f-109">Output : 'T[]</span></span>

<span data-ttu-id="feb7f-110">包含元素的陣列 `array[1..Length(array) - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="feb7f-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="feb7f-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="feb7f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="feb7f-112">不要</span><span class="sxs-lookup"><span data-stu-id="feb7f-112">'T</span></span>

<span data-ttu-id="feb7f-113">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="feb7f-113">The type of the array elements.</span></span>