---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 04738aa54ce8b719b05954824e3553388a995df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700963"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="1fc93-102">BlockEncodingByLCU 函式</span><span class="sxs-lookup"><span data-stu-id="1fc93-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="1fc93-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1fc93-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1fc93-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1fc93-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1fc93-105">將感興趣的運算子編碼為 `BlockEncoding` 。</span><span class="sxs-lookup"><span data-stu-id="1fc93-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="1fc93-106">這會建立 `BlockEncoding` 單一 $U = P\cdot V\cdot P ^ \dagger $，以將某些運算子編碼 $H = \ sum_ {j} | \ Alpha_j |Unitaries 的線性組合 U_j $。</span><span class="sxs-lookup"><span data-stu-id="1fc93-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="1fc93-107">一般來說，$P $ 是單一狀態準備，因此 $P \ket {0} \_ a = \ sum_j \sqrt{\ Alpha_j/ \| \vec\Alpha \| \_ 2} \ket{j} \_ a $ 和 $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $。</span><span class="sxs-lookup"><span data-stu-id="1fc93-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="1fc93-108">輸入</span><span class="sxs-lookup"><span data-stu-id="1fc93-108">Input</span></span>

### <a name="statepreparation--t--unit-adj--ctl"></a><span data-ttu-id="1fc93-109">statePreparation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="1fc93-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1fc93-110">單一的 $P $，可準備某個目標狀態。</span><span class="sxs-lookup"><span data-stu-id="1fc93-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit-adj--ctl"></a><span data-ttu-id="1fc93-111">選取器： ( t，) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="1fc93-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1fc93-112">將 $H $ 的元件 unitaries 編碼的單一 $V $。</span><span class="sxs-lookup"><span data-stu-id="1fc93-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit-adj--ctl"></a><span data-ttu-id="1fc93-113">輸出： ( t，) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="1fc93-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1fc93-114">單一的 $U $ 可共同處理暫存器 `a` 和 `s` 區塊編碼 $H $，並且滿足 $U ^ \Dagger = U $。</span><span class="sxs-lookup"><span data-stu-id="1fc93-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1fc93-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="1fc93-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1fc93-116">不要</span><span class="sxs-lookup"><span data-stu-id="1fc93-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="1fc93-117">者</span><span class="sxs-lookup"><span data-stu-id="1fc93-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="1fc93-118">備註</span><span class="sxs-lookup"><span data-stu-id="1fc93-118">Remarks</span></span>

<span data-ttu-id="1fc93-119">這 `BlockEncoding` 項執行會提供它的屬性 `BlockEncodingReflection` 。</span><span class="sxs-lookup"><span data-stu-id="1fc93-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fc93-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1fc93-120">See Also</span></span>

- [<span data-ttu-id="1fc93-121">BlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="1fc93-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="1fc93-122">BlockEncodingReflection。</span><span class="sxs-lookup"><span data-stu-id="1fc93-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)