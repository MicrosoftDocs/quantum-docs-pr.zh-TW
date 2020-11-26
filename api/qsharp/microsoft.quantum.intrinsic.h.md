---
uid: Microsoft.Quantum.Intrinsic.H
title: H 運算
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: H
qsharp.summary: >-
  Applies the Hadamard transformation to a single qubit.

  \begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 6f02390588c9de38f69802575429aff749f70ac5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212370"
---
# <a name="h-operation"></a><span data-ttu-id="0247d-102">H 運算</span><span class="sxs-lookup"><span data-stu-id="0247d-102">H operation</span></span>

<span data-ttu-id="0247d-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="0247d-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="0247d-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0247d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0247d-105">將 Hadamard 轉換套用至單一量子位。</span><span class="sxs-lookup"><span data-stu-id="0247d-105">Applies the Hadamard transformation to a single qubit.</span></span>

<span data-ttu-id="0247d-106">\begin{align} H \mathrel{： =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ 1 &-1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="0247d-106">\begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="0247d-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="0247d-107">\end{align}</span></span>

```qsharp
operation H (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0247d-108">輸入</span><span class="sxs-lookup"><span data-stu-id="0247d-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="0247d-109">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0247d-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0247d-110">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="0247d-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0247d-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0247d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

