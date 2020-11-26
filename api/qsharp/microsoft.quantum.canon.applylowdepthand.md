---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 4c5e381227bf82415121add38d0c0d2959fb529d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209310"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="d5766-102">ApplyLowDepthAnd 操作</span><span class="sxs-lookup"><span data-stu-id="d5766-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="d5766-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d5766-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d5766-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d5766-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d5766-105">只有在這兩個控制項量子位都是在1狀態下（具有 T-深度1），並使用度量來執行 adjoint 作業時，才會反轉指定的目標量子位。</span><span class="sxs-lookup"><span data-stu-id="d5766-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d5766-106">描述</span><span class="sxs-lookup"><span data-stu-id="d5766-106">Description</span></span>

<span data-ttu-id="d5766-107">`target`只有當兩個控制項都是1，但假設處於狀態0時，才會反轉 `target` 。</span><span class="sxs-lookup"><span data-stu-id="d5766-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="d5766-108">作業具有 T 計數4、T 深度1，且需要一個協助程式量子位，因此如果已知為0，則可能較適合 CCNOT 作業 `target` 。</span><span class="sxs-lookup"><span data-stu-id="d5766-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="d5766-109">這項作業的 adjoint 是以測量為基礎，且不需要任何 T 閘道，也不需要協助程式量子位。</span><span class="sxs-lookup"><span data-stu-id="d5766-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="d5766-110">輸入</span><span class="sxs-lookup"><span data-stu-id="d5766-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="d5766-111">control1： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d5766-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d5766-112">第一個控制項量子位</span><span class="sxs-lookup"><span data-stu-id="d5766-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="d5766-113">control2： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d5766-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d5766-114">第二個控制項量子位</span><span class="sxs-lookup"><span data-stu-id="d5766-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d5766-115">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d5766-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d5766-116">目標輔助量子位;必須處於狀態0</span><span class="sxs-lookup"><span data-stu-id="d5766-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5766-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5766-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="d5766-118">參考</span><span class="sxs-lookup"><span data-stu-id="d5766-118">References</span></span>

- <span data-ttu-id="d5766-119">Cody 的新穎結構： "容錯 Toffoli 閘道的結構"、Phys. A 87、022328、2013 [arXiv： 1212.5069](https://arxiv.org/abs/1212.5069) doi： 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="d5766-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="d5766-120">Peter Selinger：「T 深度1的量子線路」，Phys. A 87、042302、2013 [arXiv： 1210.0974](https://arxiv.org/abs/1210.0974) doi： 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="d5766-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>