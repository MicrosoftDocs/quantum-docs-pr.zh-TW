---
uid: Microsoft.Quantum.Intrinsic.R1
title: R1 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: 87302a4338af144ee6a8cec83ed1803581597482
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699799"
---
# <a name="r1-operation"></a><span data-ttu-id="cd129-102">R1 操作</span><span class="sxs-lookup"><span data-stu-id="cd129-102">R1 operation</span></span>

<span data-ttu-id="cd129-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cd129-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cd129-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd129-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd129-105">根據指定的角度，套用大約 $ \ket {1} $ 狀態的旋轉。</span><span class="sxs-lookup"><span data-stu-id="cd129-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="cd129-106">\begin{align} R_1 ( \theta) \mathrel{： =} \operatorname{diag} (1，e ^ {i\theta} ) 。</span><span class="sxs-lookup"><span data-stu-id="cd129-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="cd129-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="cd129-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="cd129-108">輸入</span><span class="sxs-lookup"><span data-stu-id="cd129-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="cd129-109">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cd129-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cd129-110">要旋轉量子位的角度。</span><span class="sxs-lookup"><span data-stu-id="cd129-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="cd129-111">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cd129-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cd129-112">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="cd129-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd129-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd129-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cd129-114">備註</span><span class="sxs-lookup"><span data-stu-id="cd129-114">Remarks</span></span>

<span data-ttu-id="cd129-115">相當於：</span><span class="sxs-lookup"><span data-stu-id="cd129-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```