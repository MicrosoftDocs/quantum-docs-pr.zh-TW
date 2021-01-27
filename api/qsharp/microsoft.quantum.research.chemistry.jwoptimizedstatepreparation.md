---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedStatePreparation
title: JWOptimizedStatePreparation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedStatePreparation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: 539736ddb04b32c877664d91e20d76facd4d7ecf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851090"
---
# <a name="jwoptimizedstatepreparation-operation"></a><span data-ttu-id="f8b1c-102">JWOptimizedStatePreparation 操作</span><span class="sxs-lookup"><span data-stu-id="f8b1c-102">JWOptimizedStatePreparation operation</span></span>

<span data-ttu-id="f8b1c-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="f8b1c-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="f8b1c-104">封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學</span><span class="sxs-lookup"><span data-stu-id="f8b1c-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="f8b1c-105">藉由佔用微調 orbitals，來準備試用狀態的簡單狀態</span><span class="sxs-lookup"><span data-stu-id="f8b1c-105">Simple state preparation of trial state by occupying spin-orbitals</span></span>

```qsharp
operation JWOptimizedStatePreparation (qubitIndices : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f8b1c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f8b1c-106">Input</span></span>

### <a name="qubitindices--int"></a><span data-ttu-id="f8b1c-107">qubitIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f8b1c-107">qubitIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f8b1c-108">電子要佔用的量子位索引。</span><span class="sxs-lookup"><span data-stu-id="f8b1c-108">Indices of qubits to be occupied by electrons.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f8b1c-109">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f8b1c-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f8b1c-110">Hamiltonian 的量子位。</span><span class="sxs-lookup"><span data-stu-id="f8b1c-110">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f8b1c-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8b1c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

