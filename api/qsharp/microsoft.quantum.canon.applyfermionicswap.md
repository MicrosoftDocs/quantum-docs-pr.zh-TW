---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218796"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="7b4e7-102">ApplyFermionicSWAP 操作</span><span class="sxs-lookup"><span data-stu-id="7b4e7-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="7b4e7-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7b4e7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7b4e7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b4e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b4e7-105">套用 Fermionic 交換。</span><span class="sxs-lookup"><span data-stu-id="7b4e7-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7b4e7-106">描述</span><span class="sxs-lookup"><span data-stu-id="7b4e7-106">Description</span></span>

<span data-ttu-id="7b4e7-107">這基本上會交換量子位，同時套用-1 的全域階段（如果兩個量子位都是1）。</span><span class="sxs-lookup"><span data-stu-id="7b4e7-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="7b4e7-108">保留 orbitals 的反 symmetrization。</span><span class="sxs-lookup"><span data-stu-id="7b4e7-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="7b4e7-109">如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="7b4e7-109">See  for more information.</span></span>

<span data-ttu-id="7b4e7-110">這項作業是以單一運算子 \begin{align} f_ {swap} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="7b4e7-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="7b4e7-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="7b4e7-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="7b4e7-112">輸入</span><span class="sxs-lookup"><span data-stu-id="7b4e7-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="7b4e7-113">qubit1： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7b4e7-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7b4e7-114">要交換的第一個量子位。</span><span class="sxs-lookup"><span data-stu-id="7b4e7-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="7b4e7-115">qubit2： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7b4e7-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7b4e7-116">要交換的第二個量子位。</span><span class="sxs-lookup"><span data-stu-id="7b4e7-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7b4e7-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b4e7-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="7b4e7-118">參考</span><span class="sxs-lookup"><span data-stu-id="7b4e7-118">References</span></span>

- [<span data-ttu-id="7b4e7-119">*Ryan Babbush、Nathan Wiebe、Jarrod McClean、James McClain、Hartmut Neven、Garnet Kin-Lic Chan*、arXiv：1706.00023</span><span class="sxs-lookup"><span data-stu-id="7b4e7-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="7b4e7-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7b4e7-120">See Also</span></span>

- [<span data-ttu-id="7b4e7-121">。 SWAP</span><span class="sxs-lookup"><span data-stu-id="7b4e7-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)