---
uid: Microsoft.Quantum.Arrays.IsEmpty
title: IsEmpty 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsEmpty
qsharp.summary: Returns true if and only if an array is empty.
ms.openlocfilehash: ae3ad8763987bab9fdae07a5fe9bd4aabef65205
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220972"
---
# <a name="isempty-function"></a><span data-ttu-id="9fb24-102">IsEmpty 函數</span><span class="sxs-lookup"><span data-stu-id="9fb24-102">IsEmpty function</span></span>

<span data-ttu-id="9fb24-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9fb24-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9fb24-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9fb24-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9fb24-105">只有當陣列是空的時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="9fb24-105">Returns true if and only if an array is empty.</span></span>

```qsharp
function IsEmpty<'T> (array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="9fb24-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9fb24-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="9fb24-107">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="9fb24-107">array : 'T[]</span></span>

<span data-ttu-id="9fb24-108">要檢查的陣列。</span><span class="sxs-lookup"><span data-stu-id="9fb24-108">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9fb24-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9fb24-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9fb24-110">`true` 只有當陣列為空時 (的長度為 0) 。</span><span class="sxs-lookup"><span data-stu-id="9fb24-110">`true` if and only if the array is empty (has length 0).</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9fb24-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="9fb24-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9fb24-112">不要</span><span class="sxs-lookup"><span data-stu-id="9fb24-112">'T</span></span>

