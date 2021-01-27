---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833310"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="69989-102">IntAsBoolArray 函式</span><span class="sxs-lookup"><span data-stu-id="69989-102">IntAsBoolArray function</span></span>

<span data-ttu-id="69989-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="69989-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="69989-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69989-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69989-105">針對傳回的陣列，使用位元組由小到大的標記法，針對非負整數產生二進位標記法。</span><span class="sxs-lookup"><span data-stu-id="69989-105">Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="69989-106">輸入</span><span class="sxs-lookup"><span data-stu-id="69989-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="69989-107">數位： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="69989-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="69989-108">要轉換成布林值陣列的非負整數。</span><span class="sxs-lookup"><span data-stu-id="69989-108">A non-negative integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="69989-109">位： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="69989-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="69989-110">二進位表示中的位數目 `number` 。</span><span class="sxs-lookup"><span data-stu-id="69989-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="69989-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="69989-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="69989-112">表示的布林值陣列 `number` 。</span><span class="sxs-lookup"><span data-stu-id="69989-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="69989-113">備註</span><span class="sxs-lookup"><span data-stu-id="69989-113">Remarks</span></span>

<span data-ttu-id="69989-114">輸入 `bits` 必須介於0到63之間。</span><span class="sxs-lookup"><span data-stu-id="69989-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="69989-115">輸入 `number` 必須介於0到 $ 2 ^ {\texttt{bits}}-$1 之間。</span><span class="sxs-lookup"><span data-stu-id="69989-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>