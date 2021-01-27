---
uid: Microsoft.Quantum.Intrinsic.R
title: R 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 1df4b1197e885e479339e542e8c1ffaeb392543d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818725"
---
# <a name="r-operation"></a><span data-ttu-id="17e5d-102">R 操作</span><span class="sxs-lookup"><span data-stu-id="17e5d-102">R operation</span></span>

<span data-ttu-id="17e5d-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="17e5d-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="17e5d-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="17e5d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="17e5d-105">針對指定的 Pauli 軸套用旋轉。</span><span class="sxs-lookup"><span data-stu-id="17e5d-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="17e5d-106">\begin{align} R_ {\mu} ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_ {\mu}/2}，\end{align} where $ \mu \in \{ i，X，Y，Z \} $。</span><span class="sxs-lookup"><span data-stu-id="17e5d-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="17e5d-107">輸入</span><span class="sxs-lookup"><span data-stu-id="17e5d-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="17e5d-108">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="17e5d-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="17e5d-109">Pauli 運算子 ($ \mu $) 要 exponentiated 以形成旋轉。</span><span class="sxs-lookup"><span data-stu-id="17e5d-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="17e5d-110">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="17e5d-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="17e5d-111">要旋轉量子位的角度。</span><span class="sxs-lookup"><span data-stu-id="17e5d-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="17e5d-112">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="17e5d-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="17e5d-113">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="17e5d-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17e5d-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17e5d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="17e5d-115">備註</span><span class="sxs-lookup"><span data-stu-id="17e5d-115">Remarks</span></span>

<span data-ttu-id="17e5d-116">以呼叫時 `pauli = PauliI` ，此作業會套用 *全域階段*。</span><span class="sxs-lookup"><span data-stu-id="17e5d-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="17e5d-117">當與仿函數搭配使用時，這個階段可能很重要 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="17e5d-117">This phase can be significant when used with the `Controlled` functor.</span></span>