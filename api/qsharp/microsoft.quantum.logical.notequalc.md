---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 0be2c97ec7b0350fc20eace76746f3ffff65fd52
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197359"
---
# <a name="notequalc-function"></a><span data-ttu-id="32ce3-102">NotEqualC 函式</span><span class="sxs-lookup"><span data-stu-id="32ce3-102">NotEqualC function</span></span>

<span data-ttu-id="32ce3-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="32ce3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="32ce3-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32ce3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32ce3-105">只有在兩個輸入不相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="32ce3-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="32ce3-106">輸入</span><span class="sxs-lookup"><span data-stu-id="32ce3-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="32ce3-107">a： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="32ce3-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="32ce3-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="32ce3-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="32ce3-109">b： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="32ce3-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="32ce3-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="32ce3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="32ce3-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="32ce3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="32ce3-112">`true` 如果和 `a` 不等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="32ce3-112">`true` if and only if `a` is not equal to `b`.</span></span>