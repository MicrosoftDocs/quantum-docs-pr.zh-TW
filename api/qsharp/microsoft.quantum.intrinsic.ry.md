---
uid: Microsoft.Quantum.Intrinsic.Ry
title: Ry 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 9966693eb7283e855f7b72e910aa3604d6c2bd61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699611"
---
# <a name="ry-operation"></a><span data-ttu-id="91a81-102">Ry 操作</span><span class="sxs-lookup"><span data-stu-id="91a81-102">Ry operation</span></span>

<span data-ttu-id="91a81-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="91a81-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="91a81-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="91a81-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="91a81-105">依指定的角度套用 $y $ 軸的旋轉。</span><span class="sxs-lookup"><span data-stu-id="91a81-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="91a81-106">\begin{align} R_y ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_y/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-\sin \frac{\theta} {2} \\ \\ \sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}。  </span><span class="sxs-lookup"><span data-stu-id="91a81-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="91a81-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="91a81-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="91a81-108">輸入</span><span class="sxs-lookup"><span data-stu-id="91a81-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="91a81-109">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="91a81-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="91a81-110">要旋轉量子位的角度。</span><span class="sxs-lookup"><span data-stu-id="91a81-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="91a81-111">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="91a81-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="91a81-112">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="91a81-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="91a81-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="91a81-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="91a81-114">備註</span><span class="sxs-lookup"><span data-stu-id="91a81-114">Remarks</span></span>

<span data-ttu-id="91a81-115">相當於：</span><span class="sxs-lookup"><span data-stu-id="91a81-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```