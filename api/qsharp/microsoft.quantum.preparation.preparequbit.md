---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 5f42bf26a8f9638ea88c035a18846050c3776b45
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700434"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="33554-102">PrepareQubit 操作</span><span class="sxs-lookup"><span data-stu-id="33554-102">PrepareQubit operation</span></span>

<span data-ttu-id="33554-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="33554-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="33554-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33554-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33554-105">準備量子位，以指定 Pauli 運算子的 + 1 (`Zero`) eigenstate。</span><span class="sxs-lookup"><span data-stu-id="33554-105">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="33554-106">如果指定了識別運算子，則會以充分混合狀態準備量子位。</span><span class="sxs-lookup"><span data-stu-id="33554-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="33554-107">如果量子位一開始是 $ \ket {0} $ 狀態，則此作業會準備指定 Pauli 操作員的 $ + $1 eigenstate 中的量子位，或者，若為 `PauliI` ，則改為在充分混合狀態中 (查看 <xref:microsoft.quantum.preparation.preparesinglequbitidentity>) 。</span><span class="sxs-lookup"><span data-stu-id="33554-107">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="33554-108">如果量子位的狀態不是 $ \ket {0} $，這項作業會套用下列閘道： $H $ for `PauliX` 、$HS $ for `PauliY` 、$I $ for `PauliZ` 和 <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` 。</span><span class="sxs-lookup"><span data-stu-id="33554-108">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="33554-109">輸入</span><span class="sxs-lookup"><span data-stu-id="33554-109">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="33554-110">基礎： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="33554-110">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="33554-111">Pauli 運算子 $P $。</span><span class="sxs-lookup"><span data-stu-id="33554-111">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="33554-112">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="33554-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="33554-113">要準備的量子位。</span><span class="sxs-lookup"><span data-stu-id="33554-113">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33554-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33554-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

