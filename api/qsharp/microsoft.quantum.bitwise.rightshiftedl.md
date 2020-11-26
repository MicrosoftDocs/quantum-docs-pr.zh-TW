---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219510"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="7095f-102">RightShiftedL 函式</span><span class="sxs-lookup"><span data-stu-id="7095f-102">RightShiftedL function</span></span>

<span data-ttu-id="7095f-103">命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="7095f-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="7095f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7095f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7095f-105">將數位的位表示右移指定的位數。</span><span class="sxs-lookup"><span data-stu-id="7095f-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="7095f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7095f-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="7095f-107">值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7095f-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7095f-108">要向右移動位標記法的數位， (較不重要的) 。</span><span class="sxs-lookup"><span data-stu-id="7095f-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="7095f-109">數量： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7095f-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7095f-110">要 `value` 向右移動的位數。</span><span class="sxs-lookup"><span data-stu-id="7095f-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="7095f-111">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7095f-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7095f-112">的值 `value` ，以位向右移位 `amount` 。</span><span class="sxs-lookup"><span data-stu-id="7095f-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="7095f-113">備註</span><span class="sxs-lookup"><span data-stu-id="7095f-113">Remarks</span></span>

<span data-ttu-id="7095f-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="7095f-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```