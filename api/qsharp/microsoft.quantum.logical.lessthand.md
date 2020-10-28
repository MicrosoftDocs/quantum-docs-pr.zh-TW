---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 8cd274d5e299df2f556006baf7457d54aebcd071
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700571"
---
# <a name="lessthand-function"></a><span data-ttu-id="39c42-102">LessThanD 函式</span><span class="sxs-lookup"><span data-stu-id="39c42-102">LessThanD function</span></span>

<span data-ttu-id="39c42-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="39c42-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="39c42-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39c42-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39c42-105">只有當數位小於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="39c42-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="39c42-106">輸入</span><span class="sxs-lookup"><span data-stu-id="39c42-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="39c42-107">a： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="39c42-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="39c42-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="39c42-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="39c42-109">b： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="39c42-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="39c42-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="39c42-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="39c42-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="39c42-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="39c42-112">`true` 只有在 `a` 嚴格小於時才會 `b` 。</span><span class="sxs-lookup"><span data-stu-id="39c42-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="39c42-113">備註</span><span class="sxs-lookup"><span data-stu-id="39c42-113">Remarks</span></span>

<span data-ttu-id="39c42-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="39c42-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```