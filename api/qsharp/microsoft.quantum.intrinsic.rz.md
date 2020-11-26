---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Rz 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: d637abf3562eb60705da517467939dc588229c39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198617"
---
# <a name="rz-operation"></a><span data-ttu-id="847e9-102">Rz 操作</span><span class="sxs-lookup"><span data-stu-id="847e9-102">Rz operation</span></span>

<span data-ttu-id="847e9-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="847e9-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="847e9-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="847e9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="847e9-105">依指定的角度套用 $z $ 軸的旋轉。</span><span class="sxs-lookup"><span data-stu-id="847e9-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="847e9-106">\begin{align} R_z ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \theta/2} \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="847e9-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="847e9-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="847e9-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="847e9-108">輸入</span><span class="sxs-lookup"><span data-stu-id="847e9-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="847e9-109">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="847e9-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="847e9-110">要旋轉量子位的角度。</span><span class="sxs-lookup"><span data-stu-id="847e9-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="847e9-111">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="847e9-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="847e9-112">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="847e9-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="847e9-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="847e9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="847e9-114">備註</span><span class="sxs-lookup"><span data-stu-id="847e9-114">Remarks</span></span>

<span data-ttu-id="847e9-115">相當於：</span><span class="sxs-lookup"><span data-stu-id="847e9-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```