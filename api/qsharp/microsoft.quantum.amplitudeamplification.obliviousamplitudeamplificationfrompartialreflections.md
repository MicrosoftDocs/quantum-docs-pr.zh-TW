---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromPartialReflections
title: ObliviousAmplitudeAmplificationFromPartialReflections 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromPartialReflections
qsharp.summary: Returns a unitary that implements oblivious amplitude amplification by specifying for partial reflections.
ms.openlocfilehash: e00578867f14947571fd595bdf876bc271c3d485
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847202"
---
# <a name="obliviousamplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="fb1f5-102">ObliviousAmplitudeAmplificationFromPartialReflections 函式</span><span class="sxs-lookup"><span data-stu-id="fb1f5-102">ObliviousAmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="fb1f5-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="fb1f5-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="fb1f5-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb1f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb1f5-105">藉由指定部分反射，傳回實無警示幅度放大的單一。</span><span class="sxs-lookup"><span data-stu-id="fb1f5-105">Returns a unitary that implements oblivious amplitude amplification by specifying for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="fb1f5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="fb1f5-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="fb1f5-107">階段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="fb1f5-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="fb1f5-108">startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="fb1f5-108">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="fb1f5-109">targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="fb1f5-109">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="fb1f5-110">signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="fb1f5-110">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>





## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="fb1f5-111">Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit)  是形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="fb1f5-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

