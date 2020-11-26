---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedStatePreparation
title: JWOptimizedStatePreparation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedStatePreparation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: a2e0c24eaa1f5326f2d531b4e7e55b2c440bc795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229846"
---
# <a name="jwoptimizedstatepreparation-operation"></a><span data-ttu-id="e7e45-102">JWOptimizedStatePreparation 操作</span><span class="sxs-lookup"><span data-stu-id="e7e45-102">JWOptimizedStatePreparation operation</span></span>

<span data-ttu-id="e7e45-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="e7e45-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="e7e45-104">封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學</span><span class="sxs-lookup"><span data-stu-id="e7e45-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="e7e45-105">藉由佔用微調 orbitals，來準備試用狀態的簡單狀態</span><span class="sxs-lookup"><span data-stu-id="e7e45-105">Simple state preparation of trial state by occupying spin-orbitals</span></span>

```qsharp
operation JWOptimizedStatePreparation (qubitIndices : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e7e45-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e7e45-106">Input</span></span>

### <a name="qubitindices--int"></a><span data-ttu-id="e7e45-107">qubitIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e7e45-107">qubitIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e7e45-108">電子要佔用的量子位索引。</span><span class="sxs-lookup"><span data-stu-id="e7e45-108">Indices of qubits to be occupied by electrons.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e7e45-109">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e7e45-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e7e45-110">Hamiltonian 的量子位。</span><span class="sxs-lookup"><span data-stu-id="e7e45-110">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e7e45-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7e45-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

