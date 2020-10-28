---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 12a650568aa5682e8fb6498808d188b154527acb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700970"
---
# <a name="preparesinglequbitidentity-operation"></a><span data-ttu-id="233fc-102">PrepareSingleQubitIdentity 操作</span><span class="sxs-lookup"><span data-stu-id="233fc-102">PrepareSingleQubitIdentity operation</span></span>

<span data-ttu-id="233fc-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="233fc-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="233fc-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="233fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="233fc-105">以充分混合狀態準備量子位。</span><span class="sxs-lookup"><span data-stu-id="233fc-105">Prepares a qubit in the maximally mixed state.</span></span>

<span data-ttu-id="233fc-106">它會藉由套用 depolarizing 通道 $ $ \begin{align} \Omega ( \rho) \mathrel{，來準備 $ \boldone/$2 狀態中的給定量子位： =} \frac {1} {4} \ sum_ {\mu \in \{ 0，1，2，3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}，\end{align} $ $ where $ \sigma \_ i $ 是 $i $ th Pauli 運算子，其中 $ \rho $ 是代表混合狀態的密度運算子。</span><span class="sxs-lookup"><span data-stu-id="233fc-106">It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.</span></span>

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="233fc-107">輸入</span><span class="sxs-lookup"><span data-stu-id="233fc-107">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="233fc-108">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="233fc-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="233fc-109">量子位，其狀態會以上述方式 depolarized。</span><span class="sxs-lookup"><span data-stu-id="233fc-109">A qubit whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="233fc-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="233fc-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="233fc-111">備註</span><span class="sxs-lookup"><span data-stu-id="233fc-111">Remarks</span></span>

<span data-ttu-id="233fc-112">混合狀態 $ \boldone/$2 描述將此作業套用至狀態的結果，會以隱含的方式描述這項作業中所做的隨機播放的預期值。</span><span class="sxs-lookup"><span data-stu-id="233fc-112">The mixed state $\boldone / 2$ describing the result of applying this operation to a state implicitly describes an expectation value over random choices made in this operation.</span></span>
<span data-ttu-id="233fc-113">因此，在任何單一應用程式中，這項作業會將純狀態對應至純虛擬狀態，但它的運作方式如預期所述。</span><span class="sxs-lookup"><span data-stu-id="233fc-113">Thus, for any single application, this operation maps pure states to pure states, but it acts as described in expectation.</span></span>
<span data-ttu-id="233fc-114">尤其是，這項作業可以在流程 tomography 中用來測量通道的 *非 unital* 元件。</span><span class="sxs-lookup"><span data-stu-id="233fc-114">In particular, this operation can be used in process tomography to measure the *non-unital* components of a channel.</span></span>