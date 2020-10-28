---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699382"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="de750-102">LeftShiftedL 函式</span><span class="sxs-lookup"><span data-stu-id="de750-102">LeftShiftedL function</span></span>

<span data-ttu-id="de750-103">命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="de750-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="de750-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de750-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de750-105">將數位的位表示向左移位指定的位數。</span><span class="sxs-lookup"><span data-stu-id="de750-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="de750-106">輸入</span><span class="sxs-lookup"><span data-stu-id="de750-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="de750-107">值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="de750-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="de750-108">要向左移動位標記法的數位， (更重要的) 。</span><span class="sxs-lookup"><span data-stu-id="de750-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="de750-109">數量： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="de750-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="de750-110">要向左移位的位數 `value` 。</span><span class="sxs-lookup"><span data-stu-id="de750-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="de750-111">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="de750-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="de750-112">的值 `value` ，以位向左移位 `amount` 。</span><span class="sxs-lookup"><span data-stu-id="de750-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="de750-113">備註</span><span class="sxs-lookup"><span data-stu-id="de750-113">Remarks</span></span>

<span data-ttu-id="de750-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="de750-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```