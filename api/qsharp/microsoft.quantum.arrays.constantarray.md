---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210058"
---
# <a name="constantarray-function"></a><span data-ttu-id="31048-102">ConstantArray 函式</span><span class="sxs-lookup"><span data-stu-id="31048-102">ConstantArray function</span></span>

<span data-ttu-id="31048-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="31048-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="31048-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31048-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="31048-105">建立指定長度的陣列，其中所有元素等於指定的值。</span><span class="sxs-lookup"><span data-stu-id="31048-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="31048-106">輸入</span><span class="sxs-lookup"><span data-stu-id="31048-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="31048-107">長度： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="31048-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="31048-108">新陣列的長度。</span><span class="sxs-lookup"><span data-stu-id="31048-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="31048-109">值： t</span><span class="sxs-lookup"><span data-stu-id="31048-109">value : 'T</span></span>

<span data-ttu-id="31048-110">新陣列的每個元素的值。</span><span class="sxs-lookup"><span data-stu-id="31048-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="31048-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="31048-111">Output : 'T[]</span></span>

<span data-ttu-id="31048-112">長度的新陣列 `length` ，因此每個元素都是 `value` 。</span><span class="sxs-lookup"><span data-stu-id="31048-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="31048-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="31048-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="31048-114">不要</span><span class="sxs-lookup"><span data-stu-id="31048-114">'T</span></span>

