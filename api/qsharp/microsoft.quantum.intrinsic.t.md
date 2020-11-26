---
uid: Microsoft.Quantum.Intrinsic.T
title: T 運算
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 352ef2c1b15a46dea85c420fc6f1cfab0382e73a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198396"
---
# <a name="t-operation"></a><span data-ttu-id="f4cd1-102">T 運算</span><span class="sxs-lookup"><span data-stu-id="f4cd1-102">T operation</span></span>

<span data-ttu-id="f4cd1-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="f4cd1-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="f4cd1-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f4cd1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f4cd1-105">將 T 閘道套用至單一量子位。</span><span class="sxs-lookup"><span data-stu-id="f4cd1-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f4cd1-106">描述</span><span class="sxs-lookup"><span data-stu-id="f4cd1-106">Description</span></span>

<span data-ttu-id="f4cd1-107">這項作業可由單一矩陣 \begin{align} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}. 模擬</span><span class="sxs-lookup"><span data-stu-id="f4cd1-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="f4cd1-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f4cd1-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="f4cd1-109">輸入</span><span class="sxs-lookup"><span data-stu-id="f4cd1-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="f4cd1-110">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f4cd1-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f4cd1-111">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="f4cd1-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f4cd1-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4cd1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

