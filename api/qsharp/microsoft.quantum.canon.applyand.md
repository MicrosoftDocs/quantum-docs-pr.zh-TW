---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: ApplyAnd 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 39ffb9c598b6345c0d63c0c0d9705d84e101cc47
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845196"
---
# <a name="applyand-operation"></a><span data-ttu-id="92fa0-102">ApplyAnd 操作</span><span class="sxs-lookup"><span data-stu-id="92fa0-102">ApplyAnd operation</span></span>

<span data-ttu-id="92fa0-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="92fa0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="92fa0-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="92fa0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="92fa0-105">只有在這兩個控制項量子位都處於1狀態時，才使用度量來執行 adjoint 作業，以反轉指定的目標量子位。</span><span class="sxs-lookup"><span data-stu-id="92fa0-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="92fa0-106">描述</span><span class="sxs-lookup"><span data-stu-id="92fa0-106">Description</span></span>

<span data-ttu-id="92fa0-107">`target`只有當兩個控制項都是1，但假設處於狀態0時，才會反轉 `target` 。</span><span class="sxs-lookup"><span data-stu-id="92fa0-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="92fa0-108">作業具有 T 計數4、T 深度2且不需要協助程式量子位，因此如果已知為0，則可能較適合 CCNOT 作業 `target` 。</span><span class="sxs-lookup"><span data-stu-id="92fa0-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="92fa0-109">這項作業的 adjoint 是以測量為基礎，且不需要任何 T 閘道。</span><span class="sxs-lookup"><span data-stu-id="92fa0-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="92fa0-110">這項作業的受控制應用程式不需要協助程式量子位、閘道，也 `2^c` `Rz` 不會針對深度優化，其中 `c` 是整體控制量子位的數目，包括作業的兩個控制項 `ApplyAnd` 。</span><span class="sxs-lookup"><span data-stu-id="92fa0-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="92fa0-111">受 adjoint 控制的應用程式需要 `2^c - 1` `Rz` 兩個角度的閘道 () 非 adjoint 作業的大小、沒有協助程式量子位，且未針對深度優化。</span><span class="sxs-lookup"><span data-stu-id="92fa0-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="92fa0-112">輸入</span><span class="sxs-lookup"><span data-stu-id="92fa0-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="92fa0-113">control1： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="92fa0-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="92fa0-114">第一個控制項量子位</span><span class="sxs-lookup"><span data-stu-id="92fa0-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="92fa0-115">control2： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="92fa0-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="92fa0-116">第二個控制項量子位</span><span class="sxs-lookup"><span data-stu-id="92fa0-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="92fa0-117">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="92fa0-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="92fa0-118">目標輔助量子位;必須處於狀態0</span><span class="sxs-lookup"><span data-stu-id="92fa0-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="92fa0-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92fa0-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="92fa0-120">參考資料</span><span class="sxs-lookup"><span data-stu-id="92fa0-120">References</span></span>

- <span data-ttu-id="92fa0-121">Cody 的新穎結構： "容錯 Toffoli 閘道的結構"、Phys. A 87、022328、2013 [arXiv： 1212.5069](https://arxiv.org/abs/1212.5069) doi： 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="92fa0-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="92fa0-122">Craig Gidney： "減半量子加法的成本"，量子2，頁面74，2018 [arXiv： 1709.06648](https://arxiv.org/abs/1709.06648) doi： 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="92fa0-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="92fa0-123">Mathias Soeken：「量子 Oracle 電路和耶誕節樹狀結構模式」， [從2019年12月19日](https://msoeken.github.io/blog_qac.html) (注意：說明多個受控制的結構) </span><span class="sxs-lookup"><span data-stu-id="92fa0-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>