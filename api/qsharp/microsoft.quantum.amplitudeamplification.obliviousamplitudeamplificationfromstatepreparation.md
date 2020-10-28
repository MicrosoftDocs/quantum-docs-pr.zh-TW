---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700098"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="55ac5-102">ObliviousAmplitudeAmplificationFromStatePreparation 函式</span><span class="sxs-lookup"><span data-stu-id="55ac5-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="55ac5-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="55ac5-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="55ac5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55ac5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55ac5-105">無警示幅度放大（依 oracle 進行部分反射）。</span><span class="sxs-lookup"><span data-stu-id="55ac5-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="55ac5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="55ac5-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="55ac5-107">階段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="55ac5-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="55ac5-108">部分反射的階段</span><span class="sxs-lookup"><span data-stu-id="55ac5-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="55ac5-109">startStateOracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="55ac5-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="55ac5-110">單一 oracle $A $ 可準備輔助啟動狀態</span><span class="sxs-lookup"><span data-stu-id="55ac5-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="55ac5-111">signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="55ac5-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="55ac5-112">單一 oracle $O $ 的型別 `ObliviousOracle` ，在輔助和系統註冊上共同運作</span><span class="sxs-lookup"><span data-stu-id="55ac5-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="55ac5-113">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55ac5-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55ac5-114">單一量子位旗標登錄的索引</span><span class="sxs-lookup"><span data-stu-id="55ac5-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="55ac5-115">Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]、[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="55ac5-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="55ac5-116">根據部分反射來實行無警示振幅放大的作業。</span><span class="sxs-lookup"><span data-stu-id="55ac5-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="55ac5-117">備註</span><span class="sxs-lookup"><span data-stu-id="55ac5-117">Remarks</span></span>

<span data-ttu-id="55ac5-118">如此一來，就能在的輔助啟動和目標狀態形式上產生更嚴格的條件，而不是 `AmpAmpObliviousByReflectionPhases` 。</span><span class="sxs-lookup"><span data-stu-id="55ac5-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="55ac5-119">假設 $A \ket {0} \_ f\ket {0} \_ A = \ket{\text{start}} \_ {fa} $ 可 \_ 從計算基礎 $ \ket {0} \_ f\ket $ 準備輔助啟動狀態 $ \ket{\text{start}} {fa} $ {0} 。</span><span class="sxs-lookup"><span data-stu-id="55ac5-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="55ac5-120">假設目標狀態是以 $ \ket {1} \_ f $ 標示。</span><span class="sxs-lookup"><span data-stu-id="55ac5-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="55ac5-121">假設 \begin{align} O\ket {\ text {start}} \_ {fa} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {任何}} \_ a\ket {\ text {target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots，\end{align} 針對某些單一 $U $。</span><span class="sxs-lookup"><span data-stu-id="55ac5-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>