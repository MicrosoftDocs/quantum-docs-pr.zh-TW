---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209769"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="fcd44-102">RightShiftedI 函式</span><span class="sxs-lookup"><span data-stu-id="fcd44-102">RightShiftedI function</span></span>

<span data-ttu-id="fcd44-103">命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="fcd44-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="fcd44-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fcd44-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fcd44-105">將數位的位表示右移指定的位數。</span><span class="sxs-lookup"><span data-stu-id="fcd44-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="fcd44-106">輸入</span><span class="sxs-lookup"><span data-stu-id="fcd44-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="fcd44-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcd44-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcd44-108">要向右移動位標記法的數位， (較不重要的) 。</span><span class="sxs-lookup"><span data-stu-id="fcd44-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="fcd44-109">數量： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcd44-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcd44-110">要 `value` 向右移動的位數。</span><span class="sxs-lookup"><span data-stu-id="fcd44-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="fcd44-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcd44-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcd44-112">的值 `value` ，以位向右移位 `amount` 。</span><span class="sxs-lookup"><span data-stu-id="fcd44-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcd44-113">備註</span><span class="sxs-lookup"><span data-stu-id="fcd44-113">Remarks</span></span>

<span data-ttu-id="fcd44-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="fcd44-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```