---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700487"
---
# <a name="bitsizei-function"></a><span data-ttu-id="d613b-102">BitSizeI 函式</span><span class="sxs-lookup"><span data-stu-id="d613b-102">BitSizeI function</span></span>

<span data-ttu-id="d613b-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d613b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d613b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d613b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d613b-105">若為非負整數，則會傳回 `a` 所需的位數來表示 `a` 。</span><span class="sxs-lookup"><span data-stu-id="d613b-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="d613b-106">也就是說，會傳回最小的 $n $，以 $a < 2 ^ n $。</span><span class="sxs-lookup"><span data-stu-id="d613b-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="d613b-107">輸入</span><span class="sxs-lookup"><span data-stu-id="d613b-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d613b-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d613b-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d613b-109">要計算其位大小的整數。</span><span class="sxs-lookup"><span data-stu-id="d613b-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="d613b-110">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d613b-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d613b-111">的位大小 `a` 。</span><span class="sxs-lookup"><span data-stu-id="d613b-111">The bit-size of `a`.</span></span>