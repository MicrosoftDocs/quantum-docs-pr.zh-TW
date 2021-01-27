---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 334f407a32dabc8f4e0a1a29c8f06a1b9f40dc59
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845060"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="addfe-102">ApplyFermionicSWAP 操作</span><span class="sxs-lookup"><span data-stu-id="addfe-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="addfe-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="addfe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="addfe-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="addfe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="addfe-105">套用 Fermionic 交換。</span><span class="sxs-lookup"><span data-stu-id="addfe-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="addfe-106">描述</span><span class="sxs-lookup"><span data-stu-id="addfe-106">Description</span></span>

<span data-ttu-id="addfe-107">這基本上會交換量子位，同時套用-1 的全域階段（如果兩個量子位都是1）。</span><span class="sxs-lookup"><span data-stu-id="addfe-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="addfe-108">保留 orbitals 的反 symmetrization。</span><span class="sxs-lookup"><span data-stu-id="addfe-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="addfe-109">如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="addfe-109">See  for more information.</span></span>

<span data-ttu-id="addfe-110">這項作業是以單一運算子 \begin{align} f_ {swap} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="addfe-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="addfe-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="addfe-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="addfe-112">輸入</span><span class="sxs-lookup"><span data-stu-id="addfe-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="addfe-113">qubit1： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="addfe-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="addfe-114">要交換的第一個量子位。</span><span class="sxs-lookup"><span data-stu-id="addfe-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="addfe-115">qubit2： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="addfe-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="addfe-116">要交換的第二個量子位。</span><span class="sxs-lookup"><span data-stu-id="addfe-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="addfe-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="addfe-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="addfe-118">參考資料</span><span class="sxs-lookup"><span data-stu-id="addfe-118">References</span></span>

- [<span data-ttu-id="addfe-119">*Ryan Babbush、Nathan Wiebe、Jarrod McClean、James McClain、Hartmut Neven、Garnet Kin-Lic Chan*、arXiv：1706.00023</span><span class="sxs-lookup"><span data-stu-id="addfe-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="addfe-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="addfe-120">See Also</span></span>

- [<span data-ttu-id="addfe-121">。 SWAP</span><span class="sxs-lookup"><span data-stu-id="addfe-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)