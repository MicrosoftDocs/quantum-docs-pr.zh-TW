---
uid: Microsoft.Quantum.Intrinsic.T
title: T 運算
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: bee252d9905aed26f6bf663f895e464e38073f44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817522"
---
# <a name="t-operation"></a><span data-ttu-id="6e2bb-102">T 運算</span><span class="sxs-lookup"><span data-stu-id="6e2bb-102">T operation</span></span>

<span data-ttu-id="6e2bb-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="6e2bb-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="6e2bb-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6e2bb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6e2bb-105">將 T 閘道套用至單一量子位。</span><span class="sxs-lookup"><span data-stu-id="6e2bb-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6e2bb-106">描述</span><span class="sxs-lookup"><span data-stu-id="6e2bb-106">Description</span></span>

<span data-ttu-id="6e2bb-107">這項作業可由單一矩陣 \begin{align} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}. 模擬</span><span class="sxs-lookup"><span data-stu-id="6e2bb-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="6e2bb-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="6e2bb-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="6e2bb-109">輸入</span><span class="sxs-lookup"><span data-stu-id="6e2bb-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="6e2bb-110">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6e2bb-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6e2bb-111">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="6e2bb-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e2bb-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e2bb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

