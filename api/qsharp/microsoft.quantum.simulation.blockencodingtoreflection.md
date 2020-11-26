---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: 742d4f5623c7c26810998f6c96e2c7b05cc452d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225341"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="2723c-102">BlockEncodingToReflection 函式</span><span class="sxs-lookup"><span data-stu-id="2723c-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="2723c-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2723c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2723c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2723c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2723c-105">將轉換 `BlockEncoding` 成相等的 `BLockEncodingReflection` 。</span><span class="sxs-lookup"><span data-stu-id="2723c-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="2723c-106">也就是說，假設有一個 `BlockEncoding` 可將某些運算子編碼 $H $ 的單一 $U $，則會將它轉換成 `BlockEncodingReflection` 編碼相同運算子的 $U ' $，但也會滿足 $U ' ^ \Dagger = U ' $。</span><span class="sxs-lookup"><span data-stu-id="2723c-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="2723c-107">這會將 $U $ 的輔助暫存器大小增加一個量子位。</span><span class="sxs-lookup"><span data-stu-id="2723c-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="2723c-108">輸入</span><span class="sxs-lookup"><span data-stu-id="2723c-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="2723c-109">blockEncoding： [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="2723c-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="2723c-110">`BlockEncoding`要轉換成反映的單一 $U $。</span><span class="sxs-lookup"><span data-stu-id="2723c-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="2723c-111">輸出： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="2723c-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="2723c-112">單一 $U ' $ 可共同處理暫存器 `a` ，並將 `s` $H $ 的區塊編碼，並滿足 $U ' ^ \Dagger = U ' $。</span><span class="sxs-lookup"><span data-stu-id="2723c-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="2723c-113">備註</span><span class="sxs-lookup"><span data-stu-id="2723c-113">Remarks</span></span>

<span data-ttu-id="2723c-114">這會將 $U $ 的輔助暫存器大小增加一個量子位。</span><span class="sxs-lookup"><span data-stu-id="2723c-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="2723c-115">參考</span><span class="sxs-lookup"><span data-stu-id="2723c-115">References</span></span>

- <span data-ttu-id="2723c-116">Hamiltonian 模擬，量子位化 Guang Hao Low，Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="2723c-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="2723c-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2723c-117">See Also</span></span>

- [<span data-ttu-id="2723c-118">BlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="2723c-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="2723c-119">BlockEncodingReflection。</span><span class="sxs-lookup"><span data-stu-id="2723c-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)