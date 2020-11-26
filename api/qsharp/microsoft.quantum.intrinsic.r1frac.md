---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: eb2dd8750ed5ad9fc75ca24bb4c8ef36298f69f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198770"
---
# <a name="r1frac-operation"></a><span data-ttu-id="4b5a5-102">R1Frac 操作</span><span class="sxs-lookup"><span data-stu-id="4b5a5-102">R1Frac operation</span></span>

<span data-ttu-id="4b5a5-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4b5a5-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4b5a5-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4b5a5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4b5a5-105">{1}以指定為 dyadic 分數的角度，套用有關 $ \ket $ 狀態的旋轉。</span><span class="sxs-lookup"><span data-stu-id="4b5a5-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="4b5a5-106">\begin{align} R_1 (n，k) \mathrel{： =} \operatorname{diag} (1，e ^ {i \pi k/2 ^ n} ) 。</span><span class="sxs-lookup"><span data-stu-id="4b5a5-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="4b5a5-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="4b5a5-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="4b5a5-108">這項作業會使用與 **相反** 的正負號慣例 @"microsoft.quantum.intrinsic.r" ，而不包含包含的 $ 1/2 $ 的因素 @"microsoft.quantum.intrinsic.r1" 。</span><span class="sxs-lookup"><span data-stu-id="4b5a5-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4b5a5-109">輸入</span><span class="sxs-lookup"><span data-stu-id="4b5a5-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="4b5a5-110">分子： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b5a5-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b5a5-111">Dyadic 分數中的分子，用來旋轉量子位的角度。</span><span class="sxs-lookup"><span data-stu-id="4b5a5-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="4b5a5-112">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b5a5-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b5a5-113">二的乘冪，指定量子位旋轉的角度的分母。</span><span class="sxs-lookup"><span data-stu-id="4b5a5-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="4b5a5-114">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4b5a5-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4b5a5-115">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="4b5a5-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b5a5-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b5a5-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4b5a5-117">備註</span><span class="sxs-lookup"><span data-stu-id="4b5a5-117">Remarks</span></span>

<span data-ttu-id="4b5a5-118">相當於：</span><span class="sxs-lookup"><span data-stu-id="4b5a5-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```