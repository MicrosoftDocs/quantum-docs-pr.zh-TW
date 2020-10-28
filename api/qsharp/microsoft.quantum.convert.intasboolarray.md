---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698290"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="6a1cb-102">IntAsBoolArray 函式</span><span class="sxs-lookup"><span data-stu-id="6a1cb-102">IntAsBoolArray function</span></span>

<span data-ttu-id="6a1cb-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="6a1cb-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="6a1cb-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a1cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6a1cb-105">針對傳回的陣列，使用位元組由小到大的標記法，產生正整數的整數表示。</span><span class="sxs-lookup"><span data-stu-id="6a1cb-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="6a1cb-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6a1cb-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="6a1cb-107">數位： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a1cb-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a1cb-108">要轉換成布林值陣列的正整數。</span><span class="sxs-lookup"><span data-stu-id="6a1cb-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="6a1cb-109">位： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a1cb-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a1cb-110">二進位表示中的位數目 `number` 。</span><span class="sxs-lookup"><span data-stu-id="6a1cb-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6a1cb-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="6a1cb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="6a1cb-112">表示的布林值陣列 `number` 。</span><span class="sxs-lookup"><span data-stu-id="6a1cb-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a1cb-113">備註</span><span class="sxs-lookup"><span data-stu-id="6a1cb-113">Remarks</span></span>

<span data-ttu-id="6a1cb-114">輸入 `bits` 必須介於0到63之間。</span><span class="sxs-lookup"><span data-stu-id="6a1cb-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="6a1cb-115">輸入 `number` 必須介於0到 $ 2 ^ {\texttt{bits}}-$1 之間。</span><span class="sxs-lookup"><span data-stu-id="6a1cb-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>