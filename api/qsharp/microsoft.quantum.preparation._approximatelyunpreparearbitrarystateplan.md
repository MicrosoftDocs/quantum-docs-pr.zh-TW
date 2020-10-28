---
uid: Microsoft.Quantum.Preparation._ApproximatelyUnprepareArbitraryStatePlan
title: _ApproximatelyUnprepareArbitraryStatePlan 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: _ApproximatelyUnprepareArbitraryStatePlan
qsharp.summary: Implementation step of arbitrary state preparation procedure.
ms.openlocfilehash: 4050a65b0830da4c3d73e84942780aa7c2643c76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700775"
---
# <a name="_approximatelyunpreparearbitrarystateplan-function"></a><span data-ttu-id="cb697-102">_ApproximatelyUnprepareArbitraryStatePlan 函式</span><span class="sxs-lookup"><span data-stu-id="cb697-102">_ApproximatelyUnprepareArbitraryStatePlan function</span></span>

<span data-ttu-id="cb697-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="cb697-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="cb697-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb697-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb697-105">任意狀態準備程式的執行步驟。</span><span class="sxs-lookup"><span data-stu-id="cb697-105">Implementation step of arbitrary state preparation procedure.</span></span>

```qsharp
function _ApproximatelyUnprepareArbitraryStatePlan (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], (rngControl : Range, idxTarget : Int)) : (Qubit[] => Unit is Adj + Ctl)[]
```


## <a name="input"></a><span data-ttu-id="cb697-106">輸入</span><span class="sxs-lookup"><span data-stu-id="cb697-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="cb697-107">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cb697-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="coefficients--complexpolar"></a><span data-ttu-id="cb697-108">係數： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="cb697-108">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>




### <a name="rngcontrol--range"></a><span data-ttu-id="cb697-109">rngControl： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="cb697-109">rngControl : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>




### <a name="idxtarget--int"></a><span data-ttu-id="cb697-110">idxTarget： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cb697-110">idxTarget : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="cb697-111">Output： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="cb697-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>



## <a name="see-also"></a><span data-ttu-id="cb697-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cb697-112">See Also</span></span>

- [<span data-ttu-id="cb697-113">PrepareArbitraryState。</span><span class="sxs-lookup"><span data-stu-id="cb697-113">Microsoft.Quantum.Preparation.PrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareArbitraryState)
- [<span data-ttu-id="cb697-114">Canon. MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="cb697-114">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)