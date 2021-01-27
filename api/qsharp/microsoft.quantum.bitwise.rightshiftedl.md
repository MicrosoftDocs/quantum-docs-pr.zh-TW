---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842104"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="0baa5-102">RightShiftedL 函式</span><span class="sxs-lookup"><span data-stu-id="0baa5-102">RightShiftedL function</span></span>

<span data-ttu-id="0baa5-103">命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="0baa5-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="0baa5-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0baa5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0baa5-105">將數位的位表示右移指定的位數。</span><span class="sxs-lookup"><span data-stu-id="0baa5-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="0baa5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0baa5-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="0baa5-107">值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0baa5-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0baa5-108">要向右移動位標記法的數位， (較不重要的) 。</span><span class="sxs-lookup"><span data-stu-id="0baa5-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="0baa5-109">數量： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0baa5-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0baa5-110">要 `value` 向右移動的位數。</span><span class="sxs-lookup"><span data-stu-id="0baa5-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="0baa5-111">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0baa5-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0baa5-112">的值 `value` ，以位向右移位 `amount` 。</span><span class="sxs-lookup"><span data-stu-id="0baa5-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="0baa5-113">備註</span><span class="sxs-lookup"><span data-stu-id="0baa5-113">Remarks</span></span>

<span data-ttu-id="0baa5-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="0baa5-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```