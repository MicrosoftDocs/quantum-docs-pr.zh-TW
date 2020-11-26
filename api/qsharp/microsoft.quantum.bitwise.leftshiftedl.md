---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 00d4f9151c620e044074930933ea2912b52534ed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219663"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="9ad61-102">LeftShiftedL 函式</span><span class="sxs-lookup"><span data-stu-id="9ad61-102">LeftShiftedL function</span></span>

<span data-ttu-id="9ad61-103">命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="9ad61-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="9ad61-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ad61-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ad61-105">將數位的位表示向左移位指定的位數。</span><span class="sxs-lookup"><span data-stu-id="9ad61-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="9ad61-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9ad61-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="9ad61-107">值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9ad61-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9ad61-108">要向左移動位標記法的數位， (更重要的) 。</span><span class="sxs-lookup"><span data-stu-id="9ad61-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="9ad61-109">數量： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ad61-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9ad61-110">要向左移位的位數 `value` 。</span><span class="sxs-lookup"><span data-stu-id="9ad61-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="9ad61-111">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9ad61-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9ad61-112">的值 `value` ，以位向左移位 `amount` 。</span><span class="sxs-lookup"><span data-stu-id="9ad61-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ad61-113">備註</span><span class="sxs-lookup"><span data-stu-id="9ad61-113">Remarks</span></span>

<span data-ttu-id="9ad61-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="9ad61-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```