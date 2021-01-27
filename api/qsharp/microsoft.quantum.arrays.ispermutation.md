---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848102"
---
# <a name="ispermutation-function"></a><span data-ttu-id="59b65-102">IsPermutation 函式</span><span class="sxs-lookup"><span data-stu-id="59b65-102">IsPermutation function</span></span>

<span data-ttu-id="59b65-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="59b65-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="59b65-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59b65-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59b65-105">只有當指定的陣列表示排列時，才會輸出 true。</span><span class="sxs-lookup"><span data-stu-id="59b65-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="59b65-106">描述</span><span class="sxs-lookup"><span data-stu-id="59b65-106">Description</span></span>

<span data-ttu-id="59b65-107">指定長度的陣列時 `array` `n` ，如果和只有在中的每個整數只出現一次，就會傳回 true， `0` 這樣就 `n - 1` `array` `array` 可以將它視為元素上的相片順序 `n` 。</span><span class="sxs-lookup"><span data-stu-id="59b65-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="59b65-108">輸入</span><span class="sxs-lookup"><span data-stu-id="59b65-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="59b65-109">permuation： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="59b65-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="59b65-110">不一定代表排列的陣列。</span><span class="sxs-lookup"><span data-stu-id="59b65-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="59b65-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="59b65-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="example"></a><span data-ttu-id="59b65-112">範例</span><span class="sxs-lookup"><span data-stu-id="59b65-112">Example</span></span>

<span data-ttu-id="59b65-113">下列 Q # 程式碼會列印「所有診斷已順利完成」訊息：</span><span class="sxs-lookup"><span data-stu-id="59b65-113">The following Q# code prints the message "All diagnostics completed successfully":</span></span>

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a><span data-ttu-id="59b65-114">備註</span><span class="sxs-lookup"><span data-stu-id="59b65-114">Remarks</span></span>

<span data-ttu-id="59b65-115">長度為零的陣列會完整排列。</span><span class="sxs-lookup"><span data-stu-id="59b65-115">An array of length zero is trivially a permutation.</span></span>