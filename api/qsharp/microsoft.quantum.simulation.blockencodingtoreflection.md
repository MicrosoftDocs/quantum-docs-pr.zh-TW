---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: a8b4c65f8c32f7f9185f1dbdacf8fc75fd4573b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700166"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="ed689-102">BlockEncodingToReflection 函式</span><span class="sxs-lookup"><span data-stu-id="ed689-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="ed689-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ed689-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ed689-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed689-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed689-105">將轉換 `BlockEncoding` 成相等的 `BLockEncodingReflection` 。</span><span class="sxs-lookup"><span data-stu-id="ed689-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="ed689-106">也就是說，假設有一個 `BlockEncoding` 可將某些運算子編碼 $H $ 的單一 $U $，則會將它轉換成 `BlockEncodingReflection` 編碼相同運算子的 $U ' $，但也會滿足 $U ' ^ \Dagger = U ' $。</span><span class="sxs-lookup"><span data-stu-id="ed689-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="ed689-107">這會將 $U $ 的輔助暫存器大小增加一個量子位。</span><span class="sxs-lookup"><span data-stu-id="ed689-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="ed689-108">輸入</span><span class="sxs-lookup"><span data-stu-id="ed689-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="ed689-109">blockEncoding： [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="ed689-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="ed689-110">`BlockEncoding`要轉換成反映的單一 $U $。</span><span class="sxs-lookup"><span data-stu-id="ed689-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="ed689-111">輸出： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="ed689-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="ed689-112">單一 $U ' $ 可共同處理暫存器 `a` ，並將 `s` $H $ 的區塊編碼，並滿足 $U ' ^ \Dagger = U ' $。</span><span class="sxs-lookup"><span data-stu-id="ed689-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed689-113">備註</span><span class="sxs-lookup"><span data-stu-id="ed689-113">Remarks</span></span>

<span data-ttu-id="ed689-114">這會將 $U $ 的輔助暫存器大小增加一個量子位。</span><span class="sxs-lookup"><span data-stu-id="ed689-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="ed689-115">參考</span><span class="sxs-lookup"><span data-stu-id="ed689-115">References</span></span>

- <span data-ttu-id="ed689-116">Hamiltonian 模擬，量子位化 Guang Hao Low，Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="ed689-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="ed689-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ed689-117">See Also</span></span>

- [<span data-ttu-id="ed689-118">BlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="ed689-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="ed689-119">BlockEncodingReflection。</span><span class="sxs-lookup"><span data-stu-id="ed689-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)