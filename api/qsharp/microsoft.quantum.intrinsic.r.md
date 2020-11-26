---
uid: Microsoft.Quantum.Intrinsic.R
title: R 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199024"
---
# <a name="r-operation"></a><span data-ttu-id="641d1-102">R 操作</span><span class="sxs-lookup"><span data-stu-id="641d1-102">R operation</span></span>

<span data-ttu-id="641d1-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="641d1-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="641d1-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="641d1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="641d1-105">針對指定的 Pauli 軸套用旋轉。</span><span class="sxs-lookup"><span data-stu-id="641d1-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="641d1-106">\begin{align} R_ {\mu} ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_ {\mu}/2}，\end{align} where $ \mu \in \{ i，X，Y，Z \} $。</span><span class="sxs-lookup"><span data-stu-id="641d1-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="641d1-107">輸入</span><span class="sxs-lookup"><span data-stu-id="641d1-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="641d1-108">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="641d1-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="641d1-109">Pauli 運算子 ($ \mu $) 要 exponentiated 以形成旋轉。</span><span class="sxs-lookup"><span data-stu-id="641d1-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="641d1-110">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="641d1-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="641d1-111">要旋轉量子位的角度。</span><span class="sxs-lookup"><span data-stu-id="641d1-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="641d1-112">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="641d1-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="641d1-113">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="641d1-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="641d1-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="641d1-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="641d1-115">備註</span><span class="sxs-lookup"><span data-stu-id="641d1-115">Remarks</span></span>

<span data-ttu-id="641d1-116">以呼叫時 `pauli = PauliI` ，此作業會套用 *全域階段*。</span><span class="sxs-lookup"><span data-stu-id="641d1-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="641d1-117">當與仿函數搭配使用時，這個階段可能很重要 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="641d1-117">This phase can be significant when used with the `Controlled` functor.</span></span>