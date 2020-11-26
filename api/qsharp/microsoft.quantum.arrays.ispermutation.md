---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220921"
---
# <a name="ispermutation-function"></a><span data-ttu-id="32e21-102">IsPermutation 函式</span><span class="sxs-lookup"><span data-stu-id="32e21-102">IsPermutation function</span></span>

<span data-ttu-id="32e21-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="32e21-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="32e21-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32e21-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32e21-105">只有當指定的陣列表示排列時，才會輸出 true。</span><span class="sxs-lookup"><span data-stu-id="32e21-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="32e21-106">描述</span><span class="sxs-lookup"><span data-stu-id="32e21-106">Description</span></span>

<span data-ttu-id="32e21-107">指定長度的陣列時 `array` `n` ，如果和只有在中的每個整數只出現一次，就會傳回 true， `0` 這樣就 `n - 1` `array` `array` 可以將它視為元素上的相片順序 `n` 。</span><span class="sxs-lookup"><span data-stu-id="32e21-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="32e21-108">輸入</span><span class="sxs-lookup"><span data-stu-id="32e21-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="32e21-109">permuation： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="32e21-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="32e21-110">不一定代表排列的陣列。</span><span class="sxs-lookup"><span data-stu-id="32e21-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="32e21-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="32e21-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="32e21-112">備註</span><span class="sxs-lookup"><span data-stu-id="32e21-112">Remarks</span></span>

<span data-ttu-id="32e21-113">長度為零的陣列會完整排列。</span><span class="sxs-lookup"><span data-stu-id="32e21-113">An array of length zero is trivially a permutation.</span></span>