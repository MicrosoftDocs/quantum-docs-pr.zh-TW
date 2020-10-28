---
uid: Microsoft.Quantum.Arrays.Reversed
title: 反轉函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699428"
---
# <a name="reversed-function"></a><span data-ttu-id="58999-102">反轉函數</span><span class="sxs-lookup"><span data-stu-id="58999-102">Reversed function</span></span>

<span data-ttu-id="58999-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="58999-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="58999-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58999-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="58999-105">建立陣列，其中包含與輸入陣列相同的元素，但以反向順序表示。</span><span class="sxs-lookup"><span data-stu-id="58999-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="58999-106">輸入</span><span class="sxs-lookup"><span data-stu-id="58999-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="58999-107">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="58999-107">array : 'T[]</span></span>

<span data-ttu-id="58999-108">要以反轉順序複製其元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="58999-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="58999-109">Output： t []</span><span class="sxs-lookup"><span data-stu-id="58999-109">Output : 'T[]</span></span>

<span data-ttu-id="58999-110">包含元素的陣列 `array[Length(array) - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="58999-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="58999-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="58999-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="58999-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="58999-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="58999-113">不要</span><span class="sxs-lookup"><span data-stu-id="58999-113">'T</span></span>

<span data-ttu-id="58999-114">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="58999-114">The type of the array elements.</span></span>