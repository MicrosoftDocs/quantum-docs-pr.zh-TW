---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: f5bacef299ab0b3627e757abdcaa798cf9b2e7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846591"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="d2619-102">IncrementByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="d2619-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="d2619-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d2619-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d2619-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2619-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2619-105">以整數常數執行量子位暫存器的模組化增量。</span><span class="sxs-lookup"><span data-stu-id="d2619-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d2619-106">描述</span><span class="sxs-lookup"><span data-stu-id="d2619-106">Description</span></span>

<span data-ttu-id="d2619-107">讓我們以 `increment` $a $）來表示， `modulus` $N $ 和以 $y $ 編碼的整數 `target` 。</span><span class="sxs-lookup"><span data-stu-id="d2619-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="d2619-108">然後，作業會執行下列轉換： \begin{align} \ket{y} \mapsto \ket{ (y + a) \operatorname{mod} N} \end{align} 整數以位元組由小到大的格式編碼。</span><span class="sxs-lookup"><span data-stu-id="d2619-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="d2619-109">輸入</span><span class="sxs-lookup"><span data-stu-id="d2619-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="d2619-110">遞增： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d2619-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d2619-111">要加入 $y $ 的整數遞增 $a $。</span><span class="sxs-lookup"><span data-stu-id="d2619-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="d2619-112">模數： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d2619-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d2619-113">Mods > $y + a $ 的整數 $N $。</span><span class="sxs-lookup"><span data-stu-id="d2619-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="d2619-114">目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d2619-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d2619-115">`LittleEndian`$A $ 新增至的格式的整數 $y $ `increment` 。</span><span class="sxs-lookup"><span data-stu-id="d2619-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d2619-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d2619-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d2619-117">備註</span><span class="sxs-lookup"><span data-stu-id="d2619-117">Remarks</span></span>

<span data-ttu-id="d2619-118">假設目標的起始值小於 $N $，而遞增 $a $ 小於 $N $。</span><span class="sxs-lookup"><span data-stu-id="d2619-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="d2619-119">請注意，會 <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> 在基礎中執行相同的作業 `PhaseLittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="d2619-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2619-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d2619-120">See Also</span></span>

- [<span data-ttu-id="d2619-121">IncrementPhaseByModularInteger。</span><span class="sxs-lookup"><span data-stu-id="d2619-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)