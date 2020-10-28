---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: ApplyAmplitudeAmplification 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: be884eab70c7f72f994baf6bd7caf05769e0d5f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700126"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="9039a-102">ApplyAmplitudeAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="9039a-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="9039a-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="9039a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="9039a-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9039a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9039a-105">在指定的暫存器上套用振幅放大，並使用一組指定的階段和 oracle 來反映初始和最終狀態。</span><span class="sxs-lookup"><span data-stu-id="9039a-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9039a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9039a-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="9039a-107">階段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="9039a-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="9039a-108">一組階段，描述振幅放大演算法之每個步驟的部分反射。</span><span class="sxs-lookup"><span data-stu-id="9039a-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="9039a-109">如需範例，請參閱 @"microsoft.quantum.amplitudeamplification.standardreflectionphases"。</span><span class="sxs-lookup"><span data-stu-id="9039a-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="9039a-110">startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="9039a-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="9039a-111">反映初始狀態的 oracle。</span><span class="sxs-lookup"><span data-stu-id="9039a-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="9039a-112">targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="9039a-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="9039a-113">反映預期最終狀態的 oracle。</span><span class="sxs-lookup"><span data-stu-id="9039a-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9039a-114">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9039a-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9039a-115">要在其上執行振幅放大的暫存器。</span><span class="sxs-lookup"><span data-stu-id="9039a-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9039a-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9039a-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

