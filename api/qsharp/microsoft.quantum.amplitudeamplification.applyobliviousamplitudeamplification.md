---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: a1bda344b1097c7ab3240bc6d9cd0d8df80b9662
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700111"
---
# <a name="applyobliviousamplitudeamplification-operation"></a><span data-ttu-id="d8aeb-102">ApplyObliviousAmplitudeAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="d8aeb-102">ApplyObliviousAmplitudeAmplification operation</span></span>

<span data-ttu-id="d8aeb-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d8aeb-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d8aeb-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d8aeb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d8aeb-105">藉由指定部分反射來無警示振幅放大。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-105">Oblivious amplitude amplification by specifying partial reflections.</span></span>

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d8aeb-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d8aeb-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="d8aeb-107">階段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="d8aeb-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="d8aeb-108">部分反射的階段</span><span class="sxs-lookup"><span data-stu-id="d8aeb-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="d8aeb-109">startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="d8aeb-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="d8aeb-110">輔助暫存器開始狀態的反映運算子</span><span class="sxs-lookup"><span data-stu-id="d8aeb-110">Reflection operator about start state of auxiliary register</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="d8aeb-111">targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="d8aeb-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="d8aeb-112">關於輔助暫存器目標狀態的反映運算子</span><span class="sxs-lookup"><span data-stu-id="d8aeb-112">Reflection operator about target state of auxiliary register</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="d8aeb-113">signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="d8aeb-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="d8aeb-114">單一 oracle $O $ 的型別 `ObliviousOracle` ，會在輔助和系統註冊上共同運作。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-114">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system registers.</span></span>


### <a name="auxiliaryregister--qubit"></a><span data-ttu-id="d8aeb-115">auxiliaryRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d8aeb-115">auxiliaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d8aeb-116">輔助暫存器</span><span class="sxs-lookup"><span data-stu-id="d8aeb-116">Auxiliary register</span></span>


### <a name="systemregister--qubit"></a><span data-ttu-id="d8aeb-117">systemRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d8aeb-117">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d8aeb-118">系統註冊</span><span class="sxs-lookup"><span data-stu-id="d8aeb-118">System register</span></span>



## <a name="output--unit"></a><span data-ttu-id="d8aeb-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8aeb-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d8aeb-120">備註</span><span class="sxs-lookup"><span data-stu-id="d8aeb-120">Remarks</span></span>

<span data-ttu-id="d8aeb-121">給定特定的輔助啟動狀態 $ \ket{\text{start}} \_ a $，特定的輔助目標狀態 $ \ket{\text{target}} \_ a $，以及任何系統狀態 $ \ket{\psi} \_ s $，假設 \begin{align} O\ket {\ text {start}} \_ a\ket {\ psi} \_ s = \lambda\ket{\text{target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\text{target} ^ \perp} \_ a\cdots \end{align} 的部分單一 $U $。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-121">Given a particular auxiliary start state $\ket{\text{start}}\_a$, a particular auxiliary target state $\ket{\text{target}}\_a$, and any system state $\ket{\psi}\_s$, suppose that \begin{align} O\ket{\text{start}}\_a\ket{\psi}\_s= \lambda\ket{\text{target}}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{\text{target}^\perp}\_a\cdots \end{align} for some unitary $U$.</span></span>
<span data-ttu-id="d8aeb-122">依應用程式和其 adjoint 在輔助暫存器上開始和目標狀態的一系列反映 `signalOracle` ，可能會改變套用 U 的成功機率。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-122">By a sequence of reflections about the start and target states on the auxiliary register interleaved by applications of `signalOracle` and its adjoint, the success probability of applying U may be altered.</span></span>

<span data-ttu-id="d8aeb-123">在大部分情況下， `auxiliaryRegister` 會以 $ \ket{\text{start}} a $ 的狀態初始化 \_ 。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-123">In most cases, `auxiliaryRegister` is initialized in the state $\ket{\text{start}}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="d8aeb-124">參考</span><span class="sxs-lookup"><span data-stu-id="d8aeb-124">References</span></span>

<span data-ttu-id="d8aeb-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="d8aeb-125">See</span></span>

- <span data-ttu-id="d8aeb-126">[ *D.W. Berry、am Childs、Cleve、Kothari、R.D. Somma （*](https://arxiv.org/abs/1312.1414) 適用于標準版本）。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma* ](https://arxiv.org/abs/1312.1414) for the standard version.</span></span>
  <span data-ttu-id="d8aeb-127">請參閱</span><span class="sxs-lookup"><span data-stu-id="d8aeb-127">See</span></span>
- <span data-ttu-id="d8aeb-128">[ *G.H. Low、I.L. Chuang*](https://arxiv.org/abs/1610.06546) for 一般化至部分反射。</span><span class="sxs-lookup"><span data-stu-id="d8aeb-128">[ *G.H. Low, I.L. Chuang* ](https://arxiv.org/abs/1610.06546) for a generalization to partial reflections.</span></span>