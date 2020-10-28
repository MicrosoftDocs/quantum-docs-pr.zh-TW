---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: a6ed0397be57ef6f14a712749cc416e1fd98b71c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700067"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="bc2e5-102">TargetStateReflectionOracle 函式</span><span class="sxs-lookup"><span data-stu-id="bc2e5-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="bc2e5-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="bc2e5-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="bc2e5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc2e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc2e5-105">`ReflectionOracle`針對旗標量子位唯一標示的目標狀態，建立相關的。</span><span class="sxs-lookup"><span data-stu-id="bc2e5-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="bc2e5-106">目標狀態的單一量子位設為1，其他所有專案0： $ \ket {1} _f $。</span><span class="sxs-lookup"><span data-stu-id="bc2e5-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="bc2e5-107">輸入</span><span class="sxs-lookup"><span data-stu-id="bc2e5-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="bc2e5-108">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bc2e5-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bc2e5-109">量子位 $f $ of oracle 旗標的索引。</span><span class="sxs-lookup"><span data-stu-id="bc2e5-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="bc2e5-110">輸出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="bc2e5-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="bc2e5-111">`ReflectionOracle`，反映 $ \ket _f $ 所標記的狀態 {1} 。</span><span class="sxs-lookup"><span data-stu-id="bc2e5-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc2e5-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bc2e5-112">See Also</span></span>

- [<span data-ttu-id="bc2e5-113">Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="bc2e5-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)