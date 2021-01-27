---
uid: Microsoft.Quantum.Arrays.IsEmpty
title: IsEmpty 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsEmpty
qsharp.summary: Returns true if and only if an array is empty.
ms.openlocfilehash: 1d402b5cfe3a42b47d4ded7064fee06a393772b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845765"
---
# <a name="isempty-function"></a><span data-ttu-id="60a09-102">IsEmpty 函數</span><span class="sxs-lookup"><span data-stu-id="60a09-102">IsEmpty function</span></span>

<span data-ttu-id="60a09-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="60a09-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="60a09-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60a09-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60a09-105">只有當陣列是空的時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="60a09-105">Returns true if and only if an array is empty.</span></span>

```qsharp
function IsEmpty<'T> (array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="60a09-106">輸入</span><span class="sxs-lookup"><span data-stu-id="60a09-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="60a09-107">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="60a09-107">array : 'T[]</span></span>

<span data-ttu-id="60a09-108">要檢查的陣列。</span><span class="sxs-lookup"><span data-stu-id="60a09-108">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="60a09-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="60a09-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="60a09-110">`true` 只有當陣列為空時 (的長度為 0) 。</span><span class="sxs-lookup"><span data-stu-id="60a09-110">`true` if and only if the array is empty (has length 0).</span></span>

## <a name="type-parameters"></a><span data-ttu-id="60a09-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="60a09-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60a09-112">不要</span><span class="sxs-lookup"><span data-stu-id="60a09-112">'T</span></span>

