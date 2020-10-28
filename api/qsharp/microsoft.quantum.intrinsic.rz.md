---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Rz 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 954b0b097d4bffcb8047a9f0c8a4c28445653c5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699782"
---
# <a name="rz-operation"></a><span data-ttu-id="1ad43-102">Rz 操作</span><span class="sxs-lookup"><span data-stu-id="1ad43-102">Rz operation</span></span>

<span data-ttu-id="1ad43-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1ad43-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1ad43-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ad43-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ad43-105">依指定的角度套用 $z $ 軸的旋轉。</span><span class="sxs-lookup"><span data-stu-id="1ad43-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="1ad43-106">\begin{align} R_z ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \theta/2} \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="1ad43-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="1ad43-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="1ad43-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="1ad43-108">輸入</span><span class="sxs-lookup"><span data-stu-id="1ad43-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="1ad43-109">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1ad43-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1ad43-110">要旋轉量子位的角度。</span><span class="sxs-lookup"><span data-stu-id="1ad43-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="1ad43-111">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1ad43-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1ad43-112">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="1ad43-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1ad43-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1ad43-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1ad43-114">備註</span><span class="sxs-lookup"><span data-stu-id="1ad43-114">Remarks</span></span>

<span data-ttu-id="1ad43-115">相當於：</span><span class="sxs-lookup"><span data-stu-id="1ad43-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```