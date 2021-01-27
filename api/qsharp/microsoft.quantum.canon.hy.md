---
uid: Microsoft.Quantum.Canon.HY
title: HY 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: 119d78c4cd8d5e5d92cb54ff652b082a1b99ae06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840452"
---
# <a name="hy-operation"></a><span data-ttu-id="8fc1a-102">HY 操作</span><span class="sxs-lookup"><span data-stu-id="8fc1a-102">HY operation</span></span>

<span data-ttu-id="8fc1a-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8fc1a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8fc1a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8fc1a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8fc1a-105">將 Y 基礎類比套用至 Hadamard 轉換，以交換 Z 軸和 Y 軸。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="8fc1a-106">在單一量子位上，Y Hadamard 轉換 $H _Y = S H $ 是：</span><span class="sxs-lookup"><span data-stu-id="8fc1a-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="8fc1a-107">\begin{align} H_Y \mathrel{： =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="8fc1a-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8fc1a-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8fc1a-109">輸入</span><span class="sxs-lookup"><span data-stu-id="8fc1a-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="8fc1a-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8fc1a-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8fc1a-111">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="8fc1a-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8fc1a-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8fc1a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8fc1a-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8fc1a-113">See Also</span></span>

- [<span data-ttu-id="8fc1a-114">...。H</span><span class="sxs-lookup"><span data-stu-id="8fc1a-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)