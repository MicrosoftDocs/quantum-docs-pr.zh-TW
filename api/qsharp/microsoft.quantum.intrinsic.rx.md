---
uid: Microsoft.Quantum.Intrinsic.Rx
title: Rx 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 6d11c8fa3c3fb2c07a88fdf2cba0ff2a7f51bf6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700575"
---
# <a name="rx-operation"></a><span data-ttu-id="669a2-102">Rx 操作</span><span class="sxs-lookup"><span data-stu-id="669a2-102">Rx operation</span></span>

<span data-ttu-id="669a2-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="669a2-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="669a2-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="669a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="669a2-105">依指定的角度套用 $x $ 軸的旋轉。</span><span class="sxs-lookup"><span data-stu-id="669a2-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="669a2-106">\begin{align} R_x ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_x/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-i\sin \frac{\theta} {2} \\ \\ -i\sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}。  </span><span class="sxs-lookup"><span data-stu-id="669a2-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="669a2-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="669a2-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="669a2-108">輸入</span><span class="sxs-lookup"><span data-stu-id="669a2-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="669a2-109">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="669a2-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="669a2-110">要旋轉量子位的角度。</span><span class="sxs-lookup"><span data-stu-id="669a2-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="669a2-111">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="669a2-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="669a2-112">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="669a2-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="669a2-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="669a2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="669a2-114">備註</span><span class="sxs-lookup"><span data-stu-id="669a2-114">Remarks</span></span>

<span data-ttu-id="669a2-115">相當於：</span><span class="sxs-lookup"><span data-stu-id="669a2-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```