---
uid: Microsoft.Quantum.Intrinsic.Rx
title: Rx 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 49638c00967ff2f47dad41acfed05868d65a24a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198583"
---
# <a name="rx-operation"></a><span data-ttu-id="a1c5d-102">Rx 操作</span><span class="sxs-lookup"><span data-stu-id="a1c5d-102">Rx operation</span></span>

<span data-ttu-id="a1c5d-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a1c5d-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a1c5d-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a1c5d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a1c5d-105">依指定的角度套用 $x $ 軸的旋轉。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="a1c5d-106">\begin{align} R_x ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_x/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-i\sin \frac{\theta} {2} \\ \\ -i\sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}。  </span><span class="sxs-lookup"><span data-stu-id="a1c5d-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="a1c5d-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a1c5d-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a1c5d-108">輸入</span><span class="sxs-lookup"><span data-stu-id="a1c5d-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="a1c5d-109">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a1c5d-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a1c5d-110">要旋轉量子位的角度。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="a1c5d-111">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a1c5d-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a1c5d-112">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a1c5d-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a1c5d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a1c5d-114">備註</span><span class="sxs-lookup"><span data-stu-id="a1c5d-114">Remarks</span></span>

<span data-ttu-id="a1c5d-115">相當於：</span><span class="sxs-lookup"><span data-stu-id="a1c5d-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```