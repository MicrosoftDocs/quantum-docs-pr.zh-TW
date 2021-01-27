---
uid: Microsoft.Quantum.Intrinsic.H
title: H 運算
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: H
qsharp.summary: >-
  Applies the Hadamard transformation to a single qubit.

  \begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 6fa712b00a2745d8c0d8d3198cc9c5e6af3e2400
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818991"
---
# <a name="h-operation"></a><span data-ttu-id="65ccb-102">H 運算</span><span class="sxs-lookup"><span data-stu-id="65ccb-102">H operation</span></span>

<span data-ttu-id="65ccb-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="65ccb-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="65ccb-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="65ccb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="65ccb-105">將 Hadamard 轉換套用至單一量子位。</span><span class="sxs-lookup"><span data-stu-id="65ccb-105">Applies the Hadamard transformation to a single qubit.</span></span>

<span data-ttu-id="65ccb-106">\begin{align} H \mathrel{： =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ 1 &-1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="65ccb-106">\begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="65ccb-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="65ccb-107">\end{align}</span></span>

```qsharp
operation H (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="65ccb-108">輸入</span><span class="sxs-lookup"><span data-stu-id="65ccb-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="65ccb-109">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="65ccb-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="65ccb-110">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="65ccb-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65ccb-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65ccb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

