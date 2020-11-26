---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 30e1cf6e353b8a4491e13a9e2f588ec9cc103cb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191596"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="ed77e-102">AmplitudeAmplificationFromStatePreparation 函式</span><span class="sxs-lookup"><span data-stu-id="ed77e-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="ed77e-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="ed77e-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="ed77e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed77e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed77e-105">部分反射的波幅放大（依 oracle）。</span><span class="sxs-lookup"><span data-stu-id="ed77e-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="ed77e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ed77e-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="ed77e-107">階段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="ed77e-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="ed77e-108">部分反射的階段</span><span class="sxs-lookup"><span data-stu-id="ed77e-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="ed77e-109">stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="ed77e-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="ed77e-110">準備開始狀態的單一 oracle $A $</span><span class="sxs-lookup"><span data-stu-id="ed77e-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="ed77e-111">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ed77e-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ed77e-112">索引至旗標量子位</span><span class="sxs-lookup"><span data-stu-id="ed77e-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="ed77e-113">輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="ed77e-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ed77e-114">一種作業，可由部分反射實作為 oracle 來執行幅度放大。</span><span class="sxs-lookup"><span data-stu-id="ed77e-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed77e-115">備註</span><span class="sxs-lookup"><span data-stu-id="ed77e-115">Remarks</span></span>

<span data-ttu-id="ed77e-116">如此一來，在開始和目標狀態的表單上會產生更嚴格的條件 `AmpAmpByReflectionPhases` 。</span><span class="sxs-lookup"><span data-stu-id="ed77e-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="ed77e-117">假設目標狀態是以 $ \ket {1} \_ f $ 標示。</span><span class="sxs-lookup"><span data-stu-id="ed77e-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="ed77e-118">假設 \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots，\end{align} 在大部分的情況下， `flagQubit` 並 `auxiliaryRegister` 在 state $ \ket {0} \_ {f} \ket {0} \_ s $ 中初始化。</span><span class="sxs-lookup"><span data-stu-id="ed77e-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>