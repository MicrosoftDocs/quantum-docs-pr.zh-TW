---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699387"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="a6c40-102">LeftShiftedI 函式</span><span class="sxs-lookup"><span data-stu-id="a6c40-102">LeftShiftedI function</span></span>

<span data-ttu-id="a6c40-103">命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="a6c40-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="a6c40-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a6c40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a6c40-105">將數位的位表示向左移位指定的位數。</span><span class="sxs-lookup"><span data-stu-id="a6c40-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="a6c40-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a6c40-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="a6c40-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a6c40-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a6c40-108">要向左移動位標記法的數位， (更重要的) 。</span><span class="sxs-lookup"><span data-stu-id="a6c40-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="a6c40-109">數量： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a6c40-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a6c40-110">要向左移位的位數 `value` 。</span><span class="sxs-lookup"><span data-stu-id="a6c40-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="a6c40-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a6c40-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a6c40-112">的值 `value` ，以位向左移位 `amount` 。</span><span class="sxs-lookup"><span data-stu-id="a6c40-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="a6c40-113">備註</span><span class="sxs-lookup"><span data-stu-id="a6c40-113">Remarks</span></span>

<span data-ttu-id="a6c40-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="a6c40-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```