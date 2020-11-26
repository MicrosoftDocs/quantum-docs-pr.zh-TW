---
uid: Microsoft.Quantum.Arrays.Head
title: Head 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221108"
---
# <a name="head-function"></a><span data-ttu-id="64494-102">Head 函數</span><span class="sxs-lookup"><span data-stu-id="64494-102">Head function</span></span>

<span data-ttu-id="64494-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="64494-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="64494-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64494-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64494-105">傳回陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="64494-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="64494-106">輸入</span><span class="sxs-lookup"><span data-stu-id="64494-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="64494-107">陣列： ' A []</span><span class="sxs-lookup"><span data-stu-id="64494-107">array : 'A[]</span></span>

<span data-ttu-id="64494-108">取得第一個元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="64494-108">Array of which the first element is taken.</span></span> <span data-ttu-id="64494-109">陣列的長度至少必須為1。</span><span class="sxs-lookup"><span data-stu-id="64494-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="64494-110">輸出： ' A</span><span class="sxs-lookup"><span data-stu-id="64494-110">Output : 'A</span></span>

<span data-ttu-id="64494-111">陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="64494-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="64494-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="64494-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="64494-113">' A</span><span class="sxs-lookup"><span data-stu-id="64494-113">'A</span></span>

<span data-ttu-id="64494-114">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="64494-114">The type of the array elements.</span></span>