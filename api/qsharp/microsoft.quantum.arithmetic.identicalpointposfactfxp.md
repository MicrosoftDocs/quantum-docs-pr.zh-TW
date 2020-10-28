---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699866"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="a5f1b-102">IdenticalPointPosFactFxP 函式</span><span class="sxs-lookup"><span data-stu-id="a5f1b-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="a5f1b-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a5f1b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a5f1b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5f1b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5f1b-105">判斷出所提供陣列中的所有固定點數位在從最小的位元數目時，都有相同的點位置。</span><span class="sxs-lookup"><span data-stu-id="a5f1b-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="a5f1b-106">亦即，陣列中所有固定點數位的位數減去點位置的位數必須是常數。</span><span class="sxs-lookup"><span data-stu-id="a5f1b-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a5f1b-107">輸入</span><span class="sxs-lookup"><span data-stu-id="a5f1b-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="a5f1b-108">fixedPoints： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="a5f1b-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="a5f1b-109">將會使用判斷提示) 檢查相容性 (的量子固定點數位陣列。</span><span class="sxs-lookup"><span data-stu-id="a5f1b-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5f1b-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5f1b-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

