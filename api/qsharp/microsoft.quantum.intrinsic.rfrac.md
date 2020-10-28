---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: RFrac 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: 9fe6aee6c7bb9e52538eae5d2caa2a6025cb85d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700578"
---
# <a name="rfrac-operation"></a><span data-ttu-id="c6500-102">RFrac 操作</span><span class="sxs-lookup"><span data-stu-id="c6500-102">RFrac operation</span></span>

<span data-ttu-id="c6500-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="c6500-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="c6500-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6500-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6500-105">使用指定為 dyadic 分數的角度，對指定的 Pauli 軸套用旋轉。</span><span class="sxs-lookup"><span data-stu-id="c6500-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="c6500-106">\begin{align} R_ {\mu} (n，k) \mathrel{： =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}，\end{align} where $ \mu \in \{ i，X，Y，Z \} $。</span><span class="sxs-lookup"><span data-stu-id="c6500-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="c6500-107">這種作業會使用與 **相反** 的正負號慣例 @"microsoft.quantum.intrinsic.r" 。</span><span class="sxs-lookup"><span data-stu-id="c6500-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="c6500-108">輸入</span><span class="sxs-lookup"><span data-stu-id="c6500-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="c6500-109">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="c6500-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="c6500-110">要 exponentiated 以形成旋轉的 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="c6500-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="c6500-111">分子： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6500-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6500-112">Dyadic 分數中的分子，用來旋轉量子位的角度。</span><span class="sxs-lookup"><span data-stu-id="c6500-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="c6500-113">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6500-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6500-114">二的乘冪，指定量子位旋轉的角度的分母。</span><span class="sxs-lookup"><span data-stu-id="c6500-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="c6500-115">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c6500-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c6500-116">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="c6500-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6500-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6500-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c6500-118">備註</span><span class="sxs-lookup"><span data-stu-id="c6500-118">Remarks</span></span>

<span data-ttu-id="c6500-119">相當於：</span><span class="sxs-lookup"><span data-stu-id="c6500-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```