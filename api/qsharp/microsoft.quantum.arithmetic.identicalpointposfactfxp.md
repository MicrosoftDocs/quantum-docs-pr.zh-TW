---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 7212f918e1d0ee86b12b85caa6e0c27bc2cebe58
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846609"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="1ee5c-102">IdenticalPointPosFactFxP 函式</span><span class="sxs-lookup"><span data-stu-id="1ee5c-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="1ee5c-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1ee5c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1ee5c-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="1ee5c-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="1ee5c-105">判斷出所提供陣列中的所有固定點數位在從最小的位元數目時，都有相同的點位置。</span><span class="sxs-lookup"><span data-stu-id="1ee5c-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="1ee5c-106">亦即，陣列中所有固定點數位的位數減去點位置的位數必須是常數。</span><span class="sxs-lookup"><span data-stu-id="1ee5c-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1ee5c-107">輸入</span><span class="sxs-lookup"><span data-stu-id="1ee5c-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="1ee5c-108">fixedPoints： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="1ee5c-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="1ee5c-109">將會使用判斷提示) 檢查相容性 (的量子固定點數位陣列。</span><span class="sxs-lookup"><span data-stu-id="1ee5c-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="1ee5c-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1ee5c-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

