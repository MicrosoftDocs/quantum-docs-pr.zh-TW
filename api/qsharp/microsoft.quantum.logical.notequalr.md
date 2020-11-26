---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197189"
---
# <a name="notequalr-function"></a><span data-ttu-id="cf82e-102">NotEqualR 函式</span><span class="sxs-lookup"><span data-stu-id="cf82e-102">NotEqualR function</span></span>

<span data-ttu-id="cf82e-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cf82e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cf82e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cf82e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cf82e-105">只有在兩個輸入不相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="cf82e-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="cf82e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="cf82e-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="cf82e-107">答：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="cf82e-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="cf82e-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="cf82e-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="cf82e-109">b：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="cf82e-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="cf82e-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="cf82e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cf82e-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cf82e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cf82e-112">`true` 如果和 `a` 不等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="cf82e-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cf82e-113">備註</span><span class="sxs-lookup"><span data-stu-id="cf82e-113">Remarks</span></span>

<span data-ttu-id="cf82e-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="cf82e-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```