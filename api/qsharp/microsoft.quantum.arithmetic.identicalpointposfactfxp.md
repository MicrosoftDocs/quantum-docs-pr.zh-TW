---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 907e270e1c3710fb346044ad7757171c6d5f568d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223046"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="51cbb-102">IdenticalPointPosFactFxP 函式</span><span class="sxs-lookup"><span data-stu-id="51cbb-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="51cbb-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="51cbb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="51cbb-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="51cbb-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="51cbb-105">判斷出所提供陣列中的所有固定點數位在從最小的位元數目時，都有相同的點位置。</span><span class="sxs-lookup"><span data-stu-id="51cbb-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="51cbb-106">亦即，陣列中所有固定點數位的位數減去點位置的位數必須是常數。</span><span class="sxs-lookup"><span data-stu-id="51cbb-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="51cbb-107">輸入</span><span class="sxs-lookup"><span data-stu-id="51cbb-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="51cbb-108">fixedPoints： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="51cbb-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="51cbb-109">將會使用判斷提示) 檢查相容性 (的量子固定點數位陣列。</span><span class="sxs-lookup"><span data-stu-id="51cbb-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="51cbb-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51cbb-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

