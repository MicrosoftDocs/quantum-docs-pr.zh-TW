---
uid: Microsoft.Quantum.Arrays.Most
title: 最多功能
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 81e66e0b64ae8dfc44d163b68370ccadd191c729
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220598"
---
# <a name="most-function"></a><span data-ttu-id="466a0-102">最多功能</span><span class="sxs-lookup"><span data-stu-id="466a0-102">Most function</span></span>

<span data-ttu-id="466a0-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="466a0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="466a0-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="466a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="466a0-105">建立等於輸入陣列的陣列，但最後一個陣列元素已卸載。</span><span class="sxs-lookup"><span data-stu-id="466a0-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="466a0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="466a0-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="466a0-107">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="466a0-107">array : 'T[]</span></span>

<span data-ttu-id="466a0-108">陣列，其優先于倒數第二個元素，以形成輸出陣列。</span><span class="sxs-lookup"><span data-stu-id="466a0-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="466a0-109">Output： t []</span><span class="sxs-lookup"><span data-stu-id="466a0-109">Output : 'T[]</span></span>

<span data-ttu-id="466a0-110">包含元素的陣列 `array[0..Length(array) - 2]` 。</span><span class="sxs-lookup"><span data-stu-id="466a0-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="466a0-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="466a0-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="466a0-112">不要</span><span class="sxs-lookup"><span data-stu-id="466a0-112">'T</span></span>

<span data-ttu-id="466a0-113">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="466a0-113">The type of the array elements.</span></span>