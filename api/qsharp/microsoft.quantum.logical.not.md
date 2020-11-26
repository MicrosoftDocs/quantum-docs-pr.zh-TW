---
uid: Microsoft.Quantum.Logical.Not
title: Not 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197444"
---
# <a name="not-function"></a><span data-ttu-id="c86ec-102">Not 函式</span><span class="sxs-lookup"><span data-stu-id="c86ec-102">Not function</span></span>

<span data-ttu-id="c86ec-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c86ec-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c86ec-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c86ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c86ec-105">傳回值的布林值否定。</span><span class="sxs-lookup"><span data-stu-id="c86ec-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="c86ec-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c86ec-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="c86ec-107">值： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c86ec-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c86ec-108">要反轉的值。</span><span class="sxs-lookup"><span data-stu-id="c86ec-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c86ec-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c86ec-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c86ec-110">`true` 如果為，則為，如果為，則 `value` 為 `false` 。</span><span class="sxs-lookup"><span data-stu-id="c86ec-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c86ec-111">備註</span><span class="sxs-lookup"><span data-stu-id="c86ec-111">Remarks</span></span>

<span data-ttu-id="c86ec-112">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="c86ec-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```