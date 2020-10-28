---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700131"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="221d0-102">AmplitudeAmplificationFromPartialReflections 函式</span><span class="sxs-lookup"><span data-stu-id="221d0-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="221d0-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="221d0-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="221d0-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="221d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="221d0-105">部分反射的波幅放大。</span><span class="sxs-lookup"><span data-stu-id="221d0-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="221d0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="221d0-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="221d0-107">階段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="221d0-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="221d0-108">部分反射的階段</span><span class="sxs-lookup"><span data-stu-id="221d0-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="221d0-109">startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="221d0-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="221d0-110">關於開始狀態的反映運算子</span><span class="sxs-lookup"><span data-stu-id="221d0-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="221d0-111">targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="221d0-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="221d0-112">目標狀態的反映運算子</span><span class="sxs-lookup"><span data-stu-id="221d0-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="221d0-113">Output： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="221d0-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="221d0-114">以部分反射來執行幅度放大的運算。</span><span class="sxs-lookup"><span data-stu-id="221d0-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="221d0-115">備註</span><span class="sxs-lookup"><span data-stu-id="221d0-115">Remarks</span></span>

<span data-ttu-id="221d0-116">振幅放大是無警示振幅放大的特殊案例，其中沒有系統量子位，且無警示 oracle 設定為 identity。</span><span class="sxs-lookup"><span data-stu-id="221d0-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="221d0-117">在大部分情況下， `startQubits` 會在狀態 $ \ket{\text{start}} $1 中初始化 \_ ，也就是的 $-$1 eigenstate `startStateReflection` 。</span><span class="sxs-lookup"><span data-stu-id="221d0-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>