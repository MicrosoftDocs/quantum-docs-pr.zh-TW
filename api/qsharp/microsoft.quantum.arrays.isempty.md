---
uid: Microsoft.Quantum.Arrays.IsEmpty
title: IsEmpty 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsEmpty
qsharp.summary: Returns true if and only if an array is empty.
ms.openlocfilehash: f658c2a25b6991d9a826706a7e95b68169901f0e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699462"
---
# <a name="isempty-function"></a><span data-ttu-id="9dbc4-102">IsEmpty 函數</span><span class="sxs-lookup"><span data-stu-id="9dbc4-102">IsEmpty function</span></span>

<span data-ttu-id="9dbc4-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9dbc4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9dbc4-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9dbc4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9dbc4-105">只有當陣列是空的時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="9dbc4-105">Returns true if and only if an array is empty.</span></span>

```qsharp
function IsEmpty<'T> (array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="9dbc4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9dbc4-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="9dbc4-107">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="9dbc4-107">array : 'T[]</span></span>

<span data-ttu-id="9dbc4-108">要檢查的陣列。</span><span class="sxs-lookup"><span data-stu-id="9dbc4-108">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9dbc4-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9dbc4-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9dbc4-110">`true` 只有當陣列為空時 (的長度為 0) 。</span><span class="sxs-lookup"><span data-stu-id="9dbc4-110">`true` if and only if the array is empty (has length 0).</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9dbc4-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="9dbc4-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9dbc4-112">不要</span><span class="sxs-lookup"><span data-stu-id="9dbc4-112">'T</span></span>

