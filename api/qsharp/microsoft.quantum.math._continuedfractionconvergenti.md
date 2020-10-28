---
uid: Microsoft.Quantum.Math._ContinuedFractionConvergentI
title: _ContinuedFractionConvergentI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: _ContinuedFractionConvergentI
qsharp.summary: Internal recursive call to calculate the GCD with a bound
ms.openlocfilehash: 849c3f72fe4c82d7256e91f07af284217f998a63
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700550"
---
# <a name="_continuedfractionconvergenti-function"></a><span data-ttu-id="48e6d-102">_ContinuedFractionConvergentI 函式</span><span class="sxs-lookup"><span data-stu-id="48e6d-102">_ContinuedFractionConvergentI function</span></span>

<span data-ttu-id="48e6d-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="48e6d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="48e6d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48e6d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48e6d-105">使用系結來計算 GCD 的內部遞迴呼叫</span><span class="sxs-lookup"><span data-stu-id="48e6d-105">Internal recursive call to calculate the GCD with a bound</span></span>

```qsharp
function _ContinuedFractionConvergentI (signA : Int, signB : Int, r : (Int, Int), s : (Int, Int), t : (Int, Int), denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a><span data-ttu-id="48e6d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="48e6d-106">Input</span></span>

### <a name="signa--int"></a><span data-ttu-id="48e6d-107">signA： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48e6d-107">signA : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="signb--int"></a><span data-ttu-id="48e6d-108">signB： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48e6d-108">signB : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="r--intint"></a><span data-ttu-id="48e6d-109">r： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) </span><span class="sxs-lookup"><span data-stu-id="48e6d-109">r : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>




### <a name="s--intint"></a><span data-ttu-id="48e6d-110">s： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) </span><span class="sxs-lookup"><span data-stu-id="48e6d-110">s : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>




### <a name="t--intint"></a><span data-ttu-id="48e6d-111">t： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) </span><span class="sxs-lookup"><span data-stu-id="48e6d-111">t : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>




### <a name="denominatorbound--int"></a><span data-ttu-id="48e6d-112">denominatorBound： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48e6d-112">denominatorBound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--fraction"></a><span data-ttu-id="48e6d-113">輸出： [分數](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="48e6d-113">Output : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>

