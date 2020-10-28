---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699512"
---
# <a name="constantarray-function"></a><span data-ttu-id="1fb39-102">ConstantArray 函式</span><span class="sxs-lookup"><span data-stu-id="1fb39-102">ConstantArray function</span></span>

<span data-ttu-id="1fb39-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1fb39-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1fb39-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1fb39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1fb39-105">建立指定長度的陣列，其中所有元素等於指定的值。</span><span class="sxs-lookup"><span data-stu-id="1fb39-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="1fb39-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1fb39-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="1fb39-107">長度： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1fb39-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1fb39-108">新陣列的長度。</span><span class="sxs-lookup"><span data-stu-id="1fb39-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="1fb39-109">值： t</span><span class="sxs-lookup"><span data-stu-id="1fb39-109">value : 'T</span></span>

<span data-ttu-id="1fb39-110">新陣列的每個元素的值。</span><span class="sxs-lookup"><span data-stu-id="1fb39-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="1fb39-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="1fb39-111">Output : 'T[]</span></span>

<span data-ttu-id="1fb39-112">長度的新陣列 `length` ，因此每個元素都是 `value` 。</span><span class="sxs-lookup"><span data-stu-id="1fb39-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1fb39-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="1fb39-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1fb39-114">不要</span><span class="sxs-lookup"><span data-stu-id="1fb39-114">'T</span></span>

