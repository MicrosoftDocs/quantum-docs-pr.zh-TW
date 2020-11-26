---
uid: Microsoft.Quantum.Intrinsic.R1
title: R1 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: a98c2cc0b309a239650afd2910cc74dffa9f899a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198804"
---
# <a name="r1-operation"></a><span data-ttu-id="c9544-102">R1 操作</span><span class="sxs-lookup"><span data-stu-id="c9544-102">R1 operation</span></span>

<span data-ttu-id="c9544-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="c9544-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="c9544-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c9544-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c9544-105">根據指定的角度，套用大約 $ \ket {1} $ 狀態的旋轉。</span><span class="sxs-lookup"><span data-stu-id="c9544-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="c9544-106">\begin{align} R_1 ( \theta) \mathrel{： =} \operatorname{diag} (1，e ^ {i\theta} ) 。</span><span class="sxs-lookup"><span data-stu-id="c9544-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="c9544-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c9544-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c9544-108">輸入</span><span class="sxs-lookup"><span data-stu-id="c9544-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="c9544-109">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c9544-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c9544-110">要旋轉量子位的角度。</span><span class="sxs-lookup"><span data-stu-id="c9544-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="c9544-111">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c9544-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c9544-112">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="c9544-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c9544-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9544-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c9544-114">備註</span><span class="sxs-lookup"><span data-stu-id="c9544-114">Remarks</span></span>

<span data-ttu-id="c9544-115">相當於：</span><span class="sxs-lookup"><span data-stu-id="c9544-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```