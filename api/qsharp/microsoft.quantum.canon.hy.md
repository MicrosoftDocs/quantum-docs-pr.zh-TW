---
uid: Microsoft.Quantum.Canon.HY
title: HY 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: ceca8eab8cb8f16333cd7a1e3c24e6cebe4ec8d7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206828"
---
# <a name="hy-operation"></a><span data-ttu-id="4a7d0-102">HY 操作</span><span class="sxs-lookup"><span data-stu-id="4a7d0-102">HY operation</span></span>

<span data-ttu-id="4a7d0-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4a7d0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4a7d0-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a7d0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a7d0-105">將 Y 基礎類比套用至 Hadamard 轉換，以交換 Z 軸和 Y 軸。</span><span class="sxs-lookup"><span data-stu-id="4a7d0-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="4a7d0-106">在單一量子位上，Y Hadamard 轉換 $H _Y = S H $ 是：</span><span class="sxs-lookup"><span data-stu-id="4a7d0-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="4a7d0-107">\begin{align} H_Y \mathrel{： =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="4a7d0-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="4a7d0-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="4a7d0-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4a7d0-109">輸入</span><span class="sxs-lookup"><span data-stu-id="4a7d0-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="4a7d0-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4a7d0-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4a7d0-111">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="4a7d0-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a7d0-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a7d0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="4a7d0-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4a7d0-113">See Also</span></span>

- [<span data-ttu-id="4a7d0-114">...。H</span><span class="sxs-lookup"><span data-stu-id="4a7d0-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)