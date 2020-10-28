---
uid: Microsoft.Quantum.Simulation._MultiplyGeneratorSystem
title: _MultiplyGeneratorSystem 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: e59700917d45f1613bbc7983bda262d3b956e2f5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697494"
---
# <a name="_multiplygeneratorsystem-function"></a><span data-ttu-id="fa201-102">_MultiplyGeneratorSystem 函式</span><span class="sxs-lookup"><span data-stu-id="fa201-102">_MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="fa201-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="fa201-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="fa201-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fa201-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fa201-105">將中所有詞彙的係數相乘 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="fa201-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function _MultiplyGeneratorSystem (multiplier : Double, idxTerm : Int, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="fa201-106">輸入</span><span class="sxs-lookup"><span data-stu-id="fa201-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="fa201-107">乘數： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fa201-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="idxterm--int"></a><span data-ttu-id="fa201-108">idxTerm： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fa201-108">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="fa201-109">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="fa201-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>





## <a name="output--generatorindex"></a><span data-ttu-id="fa201-110">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="fa201-110">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>



## <a name="remarks"></a><span data-ttu-id="fa201-111">備註</span><span class="sxs-lookup"><span data-stu-id="fa201-111">Remarks</span></span>

<span data-ttu-id="fa201-112">這是中繼步驟，不應該呼叫。</span><span class="sxs-lookup"><span data-stu-id="fa201-112">This is an intermediate step and should not be called.</span></span>