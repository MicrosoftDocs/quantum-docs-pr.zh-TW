---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: b8eff9d207752213ccdf42a9ad80fefb2da07216
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700694"
---
# <a name="blockencodingreflectionbylcu-function"></a><span data-ttu-id="bc04a-102">BlockEncodingReflectionByLCU 函式</span><span class="sxs-lookup"><span data-stu-id="bc04a-102">BlockEncodingReflectionByLCU function</span></span>

<span data-ttu-id="bc04a-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bc04a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bc04a-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc04a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc04a-105">將感興趣的運算子編碼為 `BlockEncodingReflection` 。</span><span class="sxs-lookup"><span data-stu-id="bc04a-105">Encodes an operator of interest into a `BlockEncodingReflection`.</span></span>

<span data-ttu-id="bc04a-106">這會建立 `BlockEncodingReflection` 單一 $U = P\cdot V\cdot P ^ \dagger $，以將某些運算子編碼 $H = \ sum_ {j} | \ Alpha_j |Unitaries 的線性組合 U_j $。</span><span class="sxs-lookup"><span data-stu-id="bc04a-106">This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="bc04a-107">一般來說，$P $ 是單一狀態準備，因此 $P \ket {0} \_ a \ sum_j \sqrt{\ Alpha_j/ \| \vec\Alpha \| \_ 2} \ket{j} \_ a $ 和 $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $。</span><span class="sxs-lookup"><span data-stu-id="bc04a-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="bc04a-108">輸入</span><span class="sxs-lookup"><span data-stu-id="bc04a-108">Input</span></span>

### <a name="statepreparation--qubit--unit-adj--ctl"></a><span data-ttu-id="bc04a-109">statePreparation： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="bc04a-109">statePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="bc04a-110">單一的 $P $，可準備某個目標狀態。</span><span class="sxs-lookup"><span data-stu-id="bc04a-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="bc04a-111">選取器： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]、[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="bc04a-111">selector : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="bc04a-112">將 $H $ 的元件 unitaries 編碼的單一 $V $。</span><span class="sxs-lookup"><span data-stu-id="bc04a-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="bc04a-113">輸出： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="bc04a-113">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="bc04a-114">單一 $U $ 可共同處理暫存器 `a` ，並 `s` 以區塊編碼 $H $，並且滿足 $U ' ^ {-1} = U $。</span><span class="sxs-lookup"><span data-stu-id="bc04a-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^{-1} = U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc04a-115">備註</span><span class="sxs-lookup"><span data-stu-id="bc04a-115">Remarks</span></span>

<span data-ttu-id="bc04a-116">這 `BlockEncoding` 項執行會提供它的屬性 `BlockEncodingReflection` 。</span><span class="sxs-lookup"><span data-stu-id="bc04a-116">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc04a-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bc04a-117">See Also</span></span>

- [<span data-ttu-id="bc04a-118">BlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="bc04a-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="bc04a-119">BlockEncodingReflection。</span><span class="sxs-lookup"><span data-stu-id="bc04a-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)