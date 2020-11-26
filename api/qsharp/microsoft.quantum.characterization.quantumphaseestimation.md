---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 14ba3e012f6561e7089f9fe59b2a13516b211d51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204210"
---
# <a name="quantumphaseestimation-operation"></a><span data-ttu-id="951fd-102">QuantumPhaseEstimation 操作</span><span class="sxs-lookup"><span data-stu-id="951fd-102">QuantumPhaseEstimation operation</span></span>

<span data-ttu-id="951fd-103">命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="951fd-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="951fd-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="951fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="951fd-105">針對給定的 oracle 執行量子階段估計演算法 `U` ，並將 `targetState` 該階段讀入位元組由大到小的量子暫存器中。</span><span class="sxs-lookup"><span data-stu-id="951fd-105">Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.</span></span>

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="951fd-106">輸入</span><span class="sxs-lookup"><span data-stu-id="951fd-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="951fd-107">oracle： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="951fd-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="951fd-108">為指定的整數執行 $U ^ m $ 的作業 m。</span><span class="sxs-lookup"><span data-stu-id="951fd-108">An operation implementing $U^m$ for given integer powers m.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="951fd-109">targetState： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="951fd-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="951fd-110">量子暫存器，代表 $U $ 所採取的狀態 $ \ket{\phi} $。</span><span class="sxs-lookup"><span data-stu-id="951fd-110">A quantum register representing the state $\ket{\phi}$ acted on by $U$.</span></span> <span data-ttu-id="951fd-111">如果 $ \ket{\phi} $ 是 $U $ 的 eigenstate，$U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ 表示 $ \phi \in [0，2 \ pi) $ 未知的階段。</span><span class="sxs-lookup"><span data-stu-id="951fd-111">If $\ket{\phi}$ is an eigenstate of $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi \in [0, 2\pi)$ an unknown phase.</span></span>


### <a name="controlregister--bigendian"></a><span data-ttu-id="951fd-112">controlRegister： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="951fd-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="951fd-113">以位元組由大到小的整數暫存器，可用來控制提供的 oracle，並在應用程式執行此作業後，包含 $ \phi $ 的標記法。</span><span class="sxs-lookup"><span data-stu-id="951fd-113">A big-endian representation integer register that can be used to control the provided oracle, and that will contain the a representation of $\phi$ following the application of this operation.</span></span> <span data-ttu-id="951fd-114">ControlRegister 假設是在初始狀態 $ \ket{00\cdots 0} $ 中啟動，而暫存器的長度表示所要的精確度。</span><span class="sxs-lookup"><span data-stu-id="951fd-114">The controlRegister is assumed to start in the initial state $\ket{00\cdots 0}$, where the length of the register indicates the desired precision.</span></span>



## <a name="output--unit"></a><span data-ttu-id="951fd-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="951fd-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

