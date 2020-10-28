---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dd21fcc1d0d73bd210303bfbf4f336386b912107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700567"
---
# <a name="notequald-function"></a><span data-ttu-id="0c65a-102">NotEqualD 函式</span><span class="sxs-lookup"><span data-stu-id="0c65a-102">NotEqualD function</span></span>

<span data-ttu-id="0c65a-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0c65a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0c65a-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c65a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c65a-105">只有在兩個輸入不相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="0c65a-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="0c65a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0c65a-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="0c65a-107">a： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0c65a-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0c65a-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="0c65a-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="0c65a-109">b： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0c65a-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0c65a-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="0c65a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0c65a-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0c65a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0c65a-112">`true` 如果和 `a` 不等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="0c65a-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c65a-113">備註</span><span class="sxs-lookup"><span data-stu-id="0c65a-113">Remarks</span></span>

<span data-ttu-id="0c65a-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="0c65a-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```