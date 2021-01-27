---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845315"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="d6076-102">LeftShiftedI 函式</span><span class="sxs-lookup"><span data-stu-id="d6076-102">LeftShiftedI function</span></span>

<span data-ttu-id="d6076-103">命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="d6076-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="d6076-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6076-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6076-105">將數位的位表示向左移位指定的位數。</span><span class="sxs-lookup"><span data-stu-id="d6076-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="d6076-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d6076-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="d6076-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6076-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d6076-108">要向左移動位標記法的數位， (更重要的) 。</span><span class="sxs-lookup"><span data-stu-id="d6076-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="d6076-109">數量： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6076-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d6076-110">要向左移位的位數 `value` 。</span><span class="sxs-lookup"><span data-stu-id="d6076-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="d6076-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6076-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d6076-112">的值 `value` ，以位向左移位 `amount` 。</span><span class="sxs-lookup"><span data-stu-id="d6076-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6076-113">備註</span><span class="sxs-lookup"><span data-stu-id="d6076-113">Remarks</span></span>

<span data-ttu-id="d6076-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="d6076-114">The following are equivalent:</span></span>

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```