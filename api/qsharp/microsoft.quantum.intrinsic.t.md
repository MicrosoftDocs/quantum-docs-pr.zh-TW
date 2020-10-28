---
uid: Microsoft.Quantum.Intrinsic.T
title: T 運算
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 868031386c95f65ae956b5e444c6d87d7ea0a697
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699778"
---
# <a name="t-operation"></a><span data-ttu-id="fd967-102">T 運算</span><span class="sxs-lookup"><span data-stu-id="fd967-102">T operation</span></span>

<span data-ttu-id="fd967-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="fd967-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="fd967-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fd967-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fd967-105">將 T 閘道套用至單一量子位。</span><span class="sxs-lookup"><span data-stu-id="fd967-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="fd967-106">描述</span><span class="sxs-lookup"><span data-stu-id="fd967-106">Description</span></span>

<span data-ttu-id="fd967-107">這項作業可由單一矩陣 \begin{align} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}. 模擬</span><span class="sxs-lookup"><span data-stu-id="fd967-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="fd967-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="fd967-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="fd967-109">輸入</span><span class="sxs-lookup"><span data-stu-id="fd967-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="fd967-110">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fd967-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fd967-111">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="fd967-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fd967-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fd967-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

