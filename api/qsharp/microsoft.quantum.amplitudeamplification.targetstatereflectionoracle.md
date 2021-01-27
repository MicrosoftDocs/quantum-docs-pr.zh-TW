---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 4169ccf3e210e27f779311553b845ea04f2c7dc6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843895"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="4af1f-102">TargetStateReflectionOracle 函式</span><span class="sxs-lookup"><span data-stu-id="4af1f-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="4af1f-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="4af1f-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="4af1f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4af1f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4af1f-105">`ReflectionOracle`針對旗標量子位唯一標示的目標狀態，建立相關的。</span><span class="sxs-lookup"><span data-stu-id="4af1f-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="4af1f-106">目標狀態的單一量子位設為1，其他所有專案0： $ \ket {1} _f $。</span><span class="sxs-lookup"><span data-stu-id="4af1f-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="4af1f-107">輸入</span><span class="sxs-lookup"><span data-stu-id="4af1f-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="4af1f-108">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4af1f-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4af1f-109">量子位 $f $ of oracle 旗標的索引。</span><span class="sxs-lookup"><span data-stu-id="4af1f-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="4af1f-110">輸出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="4af1f-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="4af1f-111">`ReflectionOracle`，反映 $ \ket _f $ 所標記的狀態 {1} 。</span><span class="sxs-lookup"><span data-stu-id="4af1f-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="4af1f-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4af1f-112">See Also</span></span>

- [<span data-ttu-id="4af1f-113">Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="4af1f-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)