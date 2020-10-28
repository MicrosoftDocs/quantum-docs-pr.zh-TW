---
uid: Microsoft.Quantum.Logical.Not
title: Not 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697263"
---
# <a name="not-function"></a><span data-ttu-id="7b8b8-102">Not 函式</span><span class="sxs-lookup"><span data-stu-id="7b8b8-102">Not function</span></span>

<span data-ttu-id="7b8b8-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7b8b8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7b8b8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b8b8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7b8b8-105">傳回值的布林值否定。</span><span class="sxs-lookup"><span data-stu-id="7b8b8-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="7b8b8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7b8b8-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="7b8b8-107">值： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7b8b8-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7b8b8-108">要反轉的值。</span><span class="sxs-lookup"><span data-stu-id="7b8b8-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7b8b8-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7b8b8-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7b8b8-110">`true` 如果為，則為，如果為，則 `value` 為 `false` 。</span><span class="sxs-lookup"><span data-stu-id="7b8b8-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7b8b8-111">備註</span><span class="sxs-lookup"><span data-stu-id="7b8b8-111">Remarks</span></span>

<span data-ttu-id="7b8b8-112">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="7b8b8-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```