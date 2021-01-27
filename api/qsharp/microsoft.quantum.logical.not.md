---
uid: Microsoft.Quantum.Logical.Not
title: Not 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849080"
---
# <a name="not-function"></a><span data-ttu-id="07833-102">Not 函式</span><span class="sxs-lookup"><span data-stu-id="07833-102">Not function</span></span>

<span data-ttu-id="07833-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="07833-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="07833-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="07833-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="07833-105">傳回值的布林值否定。</span><span class="sxs-lookup"><span data-stu-id="07833-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="07833-106">輸入</span><span class="sxs-lookup"><span data-stu-id="07833-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="07833-107">值： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="07833-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="07833-108">要反轉的值。</span><span class="sxs-lookup"><span data-stu-id="07833-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="07833-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="07833-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="07833-110">`true` 如果為，則為，如果為，則 `value` 為 `false` 。</span><span class="sxs-lookup"><span data-stu-id="07833-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="07833-111">備註</span><span class="sxs-lookup"><span data-stu-id="07833-111">Remarks</span></span>

<span data-ttu-id="07833-112">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="07833-112">The following are equivalent:</span></span>

```qsharp
let x = not value;
let x = Not(value);
```