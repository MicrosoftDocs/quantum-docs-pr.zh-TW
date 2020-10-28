---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 73d63936f02a52dfbbad7b8575110177a9e4463d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701074"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="e6d63-102">ApplyXControlledOnTruthTable 操作</span><span class="sxs-lookup"><span data-stu-id="e6d63-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="e6d63-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e6d63-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e6d63-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e6d63-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e6d63-105">@"microsoft.quantum.intrinsic.x" `target` 如果布耳函數 `func` 針對中的傳統指派評估為 true，則會在上套用運算 `controlRegister` 。</span><span class="sxs-lookup"><span data-stu-id="e6d63-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="e6d63-106">描述</span><span class="sxs-lookup"><span data-stu-id="e6d63-106">Description</span></span>

<span data-ttu-id="e6d63-107">作業會執行單一作業 \begin{align} U\ket {x} \ ket {y} = \ket{x}\ket{y \oplus f (x) } \end{align}，其中 $x $ 和 $y $ `controlRegister` 分別代表和 `target` 。</span><span class="sxs-lookup"><span data-stu-id="e6d63-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="e6d63-108">布耳函數 $f $ 會以大整數的形式表示為事實資料表。</span><span class="sxs-lookup"><span data-stu-id="e6d63-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="e6d63-109">例如，在三個輸入上的多數函數會以 bitstring 表示 `11101000` ，其中最重要的位會 `1` 對應至輸入指派 `(1, 1, 1)` ，而最小的位會 `0` 對應至輸入指派 `(0, 0, 0)` 。</span><span class="sxs-lookup"><span data-stu-id="e6d63-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="e6d63-110">它可以使用十六進位標記法中的大整數來表示， `0xE8L` 或以 `232L` 十進位標記法表示。</span><span class="sxs-lookup"><span data-stu-id="e6d63-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="e6d63-111">`L`尾碼表示常數的型別為 `BigInt` 。</span><span class="sxs-lookup"><span data-stu-id="e6d63-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="e6d63-112">您也可以在 [事實資料表 kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)中找到此標記法的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e6d63-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="e6d63-113">執行會使用和網 @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" 關。</span><span class="sxs-lookup"><span data-stu-id="e6d63-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="e6d63-114">輸入</span><span class="sxs-lookup"><span data-stu-id="e6d63-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="e6d63-115">func： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e6d63-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e6d63-116">以大整數表示的布林事實資料表</span><span class="sxs-lookup"><span data-stu-id="e6d63-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="e6d63-117">controlRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e6d63-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e6d63-118">註冊控制項量子位</span><span class="sxs-lookup"><span data-stu-id="e6d63-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e6d63-119">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e6d63-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e6d63-120">目標量子位</span><span class="sxs-lookup"><span data-stu-id="e6d63-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6d63-121">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6d63-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e6d63-122">參考</span><span class="sxs-lookup"><span data-stu-id="e6d63-122">References</span></span>

- [<span data-ttu-id="e6d63-123">*N. Schuch* 、 *J Siewert* 、PRL 91、no. 027902、2003、arXiv： quant-ph/0303063</span><span class="sxs-lookup"><span data-stu-id="e6d63-123">*N. Schuch* , *J. Siewert* , PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="e6d63-124">*Mathias Soeken* 、 *聖馬丁 Roetteler* 、arXiv：2005.12310</span><span class="sxs-lookup"><span data-stu-id="e6d63-124">*Mathias Soeken* , *Martin Roetteler* , arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="e6d63-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e6d63-125">See Also</span></span>

- [<span data-ttu-id="e6d63-126">ApplyXControlledOnTruthTableWithCleanTarget。</span><span class="sxs-lookup"><span data-stu-id="e6d63-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)