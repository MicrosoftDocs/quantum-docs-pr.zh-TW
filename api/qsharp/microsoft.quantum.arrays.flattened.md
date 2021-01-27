---
uid: Microsoft.Quantum.Arrays.Flattened
title: 壓平合併函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848624"
---
# <a name="flattened-function"></a><span data-ttu-id="26a61-102">壓平合併函式</span><span class="sxs-lookup"><span data-stu-id="26a61-102">Flattened function</span></span>

<span data-ttu-id="26a61-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="26a61-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="26a61-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26a61-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26a61-105">指定陣列的陣列時，會傳回所有陣列的串連。</span><span class="sxs-lookup"><span data-stu-id="26a61-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="26a61-106">輸入</span><span class="sxs-lookup"><span data-stu-id="26a61-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="26a61-107">陣列： t [] []</span><span class="sxs-lookup"><span data-stu-id="26a61-107">arrays : 'T[][]</span></span>

<span data-ttu-id="26a61-108">陣列的陣列。</span><span class="sxs-lookup"><span data-stu-id="26a61-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="26a61-109">Output： t []</span><span class="sxs-lookup"><span data-stu-id="26a61-109">Output : 'T[]</span></span>

<span data-ttu-id="26a61-110">所有陣列的串連。</span><span class="sxs-lookup"><span data-stu-id="26a61-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="26a61-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="26a61-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="26a61-112">不要</span><span class="sxs-lookup"><span data-stu-id="26a61-112">'T</span></span>

<span data-ttu-id="26a61-113">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="26a61-113">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="26a61-114">範例</span><span class="sxs-lookup"><span data-stu-id="26a61-114">Example</span></span>

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```