---
uid: Microsoft.Quantum.Logical.Xor
title: Xor 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: afb94bd1fd0b791a9a7d84bc28b0cc2baf9a0938
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197087"
---
# <a name="xor-function"></a><span data-ttu-id="ff2e8-102">Xor 函數</span><span class="sxs-lookup"><span data-stu-id="ff2e8-102">Xor function</span></span>

<span data-ttu-id="ff2e8-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ff2e8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ff2e8-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ff2e8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ff2e8-105">傳回兩個值的布林專屬分隔分離。</span><span class="sxs-lookup"><span data-stu-id="ff2e8-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="ff2e8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ff2e8-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="ff2e8-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ff2e8-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ff2e8-108">要考慮的第一個值。</span><span class="sxs-lookup"><span data-stu-id="ff2e8-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="ff2e8-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ff2e8-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ff2e8-110">要考慮的第二個值。</span><span class="sxs-lookup"><span data-stu-id="ff2e8-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ff2e8-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ff2e8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ff2e8-112">`true` 只有當和都只有一個時，才 `a` `b` 會 `true` 。</span><span class="sxs-lookup"><span data-stu-id="ff2e8-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>