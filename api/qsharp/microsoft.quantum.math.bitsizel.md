---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: c94d873d7117fd2ee66226fab6d4bfc5b33bc46d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848918"
---
# <a name="bitsizel-function"></a><span data-ttu-id="e5e75-102">BitSizeL 函式</span><span class="sxs-lookup"><span data-stu-id="e5e75-102">BitSizeL function</span></span>

<span data-ttu-id="e5e75-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e5e75-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e5e75-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5e75-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5e75-105">若為非負整數，則會傳回 `a` 所需的位數來表示 `a` 。</span><span class="sxs-lookup"><span data-stu-id="e5e75-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="e5e75-106">也就是說，會傳回最小的 $n $，以 $a < 2 ^ n $。</span><span class="sxs-lookup"><span data-stu-id="e5e75-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="e5e75-107">輸入</span><span class="sxs-lookup"><span data-stu-id="e5e75-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e5e75-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e5e75-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e5e75-109">要計算其位大小的整數。</span><span class="sxs-lookup"><span data-stu-id="e5e75-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="e5e75-110">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5e75-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e5e75-111">的位大小 `a` 。</span><span class="sxs-lookup"><span data-stu-id="e5e75-111">The bit-size of `a`.</span></span>