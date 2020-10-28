---
uid: Microsoft.Quantum.Canon.HY
title: HY 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: bc3417ff948b718be5b96513f30f3e2714b9e20c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699016"
---
# <a name="hy-operation"></a><span data-ttu-id="2c1c7-102">HY 操作</span><span class="sxs-lookup"><span data-stu-id="2c1c7-102">HY operation</span></span>

<span data-ttu-id="2c1c7-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2c1c7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2c1c7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c1c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c1c7-105">將 Y 基礎類比套用至 Hadamard 轉換，以交換 Z 軸和 Y 軸。</span><span class="sxs-lookup"><span data-stu-id="2c1c7-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="2c1c7-106">在單一量子位上，Y Hadamard 轉換 $H _Y = S H $ 是：</span><span class="sxs-lookup"><span data-stu-id="2c1c7-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="2c1c7-107">\begin{align} H_Y \mathrel{： =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="2c1c7-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="2c1c7-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2c1c7-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="2c1c7-109">輸入</span><span class="sxs-lookup"><span data-stu-id="2c1c7-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="2c1c7-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2c1c7-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2c1c7-111">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="2c1c7-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c1c7-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c1c7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2c1c7-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2c1c7-113">See Also</span></span>

- [<span data-ttu-id="2c1c7-114">...。H</span><span class="sxs-lookup"><span data-stu-id="2c1c7-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)