---
uid: Microsoft.Quantum.Arrays.Flattened
title: 壓平合併函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699483"
---
# <a name="flattened-function"></a><span data-ttu-id="6a65f-102">壓平合併函式</span><span class="sxs-lookup"><span data-stu-id="6a65f-102">Flattened function</span></span>

<span data-ttu-id="6a65f-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6a65f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6a65f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a65f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6a65f-105">指定陣列的陣列時，會傳回所有陣列的串連。</span><span class="sxs-lookup"><span data-stu-id="6a65f-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="6a65f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6a65f-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="6a65f-107">陣列： t [] []</span><span class="sxs-lookup"><span data-stu-id="6a65f-107">arrays : 'T[][]</span></span>

<span data-ttu-id="6a65f-108">陣列的陣列。</span><span class="sxs-lookup"><span data-stu-id="6a65f-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="6a65f-109">Output： t []</span><span class="sxs-lookup"><span data-stu-id="6a65f-109">Output : 'T[]</span></span>

<span data-ttu-id="6a65f-110">所有陣列的串連。</span><span class="sxs-lookup"><span data-stu-id="6a65f-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6a65f-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="6a65f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a65f-112">不要</span><span class="sxs-lookup"><span data-stu-id="6a65f-112">'T</span></span>

<span data-ttu-id="6a65f-113">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="6a65f-113">The type of `array` elements.</span></span>