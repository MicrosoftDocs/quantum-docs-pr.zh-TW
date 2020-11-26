---
uid: Microsoft.Quantum.Arrays.Flattened
title: 壓平合併函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221210"
---
# <a name="flattened-function"></a><span data-ttu-id="ed4a9-102">壓平合併函式</span><span class="sxs-lookup"><span data-stu-id="ed4a9-102">Flattened function</span></span>

<span data-ttu-id="ed4a9-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ed4a9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ed4a9-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed4a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed4a9-105">指定陣列的陣列時，會傳回所有陣列的串連。</span><span class="sxs-lookup"><span data-stu-id="ed4a9-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ed4a9-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ed4a9-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="ed4a9-107">陣列： t [] []</span><span class="sxs-lookup"><span data-stu-id="ed4a9-107">arrays : 'T[][]</span></span>

<span data-ttu-id="ed4a9-108">陣列的陣列。</span><span class="sxs-lookup"><span data-stu-id="ed4a9-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="ed4a9-109">Output： t []</span><span class="sxs-lookup"><span data-stu-id="ed4a9-109">Output : 'T[]</span></span>

<span data-ttu-id="ed4a9-110">所有陣列的串連。</span><span class="sxs-lookup"><span data-stu-id="ed4a9-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ed4a9-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="ed4a9-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ed4a9-112">不要</span><span class="sxs-lookup"><span data-stu-id="ed4a9-112">'T</span></span>

<span data-ttu-id="ed4a9-113">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="ed4a9-113">The type of `array` elements.</span></span>