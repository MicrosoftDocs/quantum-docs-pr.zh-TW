---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699322"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="a4e4d-102">ApplyFermionicSWAP 操作</span><span class="sxs-lookup"><span data-stu-id="a4e4d-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="a4e4d-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a4e4d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a4e4d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a4e4d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a4e4d-105">套用 Fermionic 交換。</span><span class="sxs-lookup"><span data-stu-id="a4e4d-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="a4e4d-106">描述</span><span class="sxs-lookup"><span data-stu-id="a4e4d-106">Description</span></span>

<span data-ttu-id="a4e4d-107">這基本上會交換量子位，同時套用-1 的全域階段（如果兩個量子位都是1）。</span><span class="sxs-lookup"><span data-stu-id="a4e4d-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="a4e4d-108">保留 orbitals 的反 symmetrization。</span><span class="sxs-lookup"><span data-stu-id="a4e4d-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="a4e4d-109">如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="a4e4d-109">See  for more information.</span></span>

<span data-ttu-id="a4e4d-110">這項作業是以單一運算子 \begin{align} f_ {swap} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="a4e4d-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="a4e4d-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a4e4d-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="a4e4d-112">輸入</span><span class="sxs-lookup"><span data-stu-id="a4e4d-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="a4e4d-113">qubit1： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a4e4d-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a4e4d-114">要交換的第一個量子位。</span><span class="sxs-lookup"><span data-stu-id="a4e4d-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="a4e4d-115">qubit2： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a4e4d-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a4e4d-116">要交換的第二個量子位。</span><span class="sxs-lookup"><span data-stu-id="a4e4d-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a4e4d-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4e4d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="a4e4d-118">參考</span><span class="sxs-lookup"><span data-stu-id="a4e4d-118">References</span></span>

- [<span data-ttu-id="a4e4d-119">*Ryan Babbush、Nathan Wiebe、Jarrod McClean、James McClain、Hartmut Neven、Garnet Kin-Lic Chan* 、arXiv：1706.00023</span><span class="sxs-lookup"><span data-stu-id="a4e4d-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="a4e4d-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a4e4d-120">See Also</span></span>

- [<span data-ttu-id="a4e4d-121">。 SWAP</span><span class="sxs-lookup"><span data-stu-id="a4e4d-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)