---
uid: Microsoft.Quantum.Arrays.Head
title: Head 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848564"
---
# <a name="head-function"></a><span data-ttu-id="9033a-102">Head 函數</span><span class="sxs-lookup"><span data-stu-id="9033a-102">Head function</span></span>

<span data-ttu-id="9033a-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9033a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9033a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9033a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9033a-105">傳回陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="9033a-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="9033a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9033a-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="9033a-107">陣列： ' A []</span><span class="sxs-lookup"><span data-stu-id="9033a-107">array : 'A[]</span></span>

<span data-ttu-id="9033a-108">取得第一個元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="9033a-108">Array of which the first element is taken.</span></span> <span data-ttu-id="9033a-109">陣列的長度至少必須為1。</span><span class="sxs-lookup"><span data-stu-id="9033a-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="9033a-110">輸出： ' A</span><span class="sxs-lookup"><span data-stu-id="9033a-110">Output : 'A</span></span>

<span data-ttu-id="9033a-111">陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="9033a-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9033a-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="9033a-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="9033a-113">' A</span><span class="sxs-lookup"><span data-stu-id="9033a-113">'A</span></span>

<span data-ttu-id="9033a-114">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="9033a-114">The type of the array elements.</span></span>