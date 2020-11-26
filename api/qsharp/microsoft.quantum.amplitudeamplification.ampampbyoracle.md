---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpByOracle
title: AmpAmpByOracle 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpByOracle
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpByOracle has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.standardamplitudeamplification".
ms.openlocfilehash: bd9cb0ae54d6b09a1945df80b6c62c1e966fd282
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191817"
---
# <a name="ampampbyoracle-function"></a><span data-ttu-id="1b986-102">AmpAmpByOracle 函式</span><span class="sxs-lookup"><span data-stu-id="1b986-102">AmpAmpByOracle function</span></span>

<span data-ttu-id="1b986-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="1b986-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="1b986-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b986-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="1b986-105">AmpAmpByOracle 已被取代。</span><span class="sxs-lookup"><span data-stu-id="1b986-105">AmpAmpByOracle has been deprecated.</span></span> <span data-ttu-id="1b986-106">請改用 <xref:Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification>。</span><span class="sxs-lookup"><span data-stu-id="1b986-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification> instead.</span></span>
>
> <span data-ttu-id="1b986-107">請使用 @"microsoft.quantum.amplitudeamplification.standardamplitudeamplification"。</span><span class="sxs-lookup"><span data-stu-id="1b986-107">Please use @"microsoft.quantum.amplitudeamplification.standardamplitudeamplification".</span></span>



```qsharp
function AmpAmpByOracle (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="1b986-108">輸入</span><span class="sxs-lookup"><span data-stu-id="1b986-108">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="1b986-109">nIterations： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b986-109">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="stateoracle--stateoracle"></a><span data-ttu-id="1b986-110">stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="1b986-110">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>




### <a name="idxflagqubit--int"></a><span data-ttu-id="1b986-111">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b986-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="1b986-112">輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="1b986-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

