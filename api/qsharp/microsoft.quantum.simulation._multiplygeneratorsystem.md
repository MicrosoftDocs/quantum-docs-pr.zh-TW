---
uid: Microsoft.Quantum.Simulation._MultiplyGeneratorSystem
title: _MultiplyGeneratorSystem 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 9fdc52bdea69e9507510a51be258eaba8e61f673
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229676"
---
# <a name="_multiplygeneratorsystem-function"></a><span data-ttu-id="95706-102">_MultiplyGeneratorSystem 函式</span><span class="sxs-lookup"><span data-stu-id="95706-102">_MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="95706-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="95706-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="95706-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95706-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95706-105">將中所有詞彙的係數相乘 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="95706-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function _MultiplyGeneratorSystem (multiplier : Double, idxTerm : Int, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="95706-106">輸入</span><span class="sxs-lookup"><span data-stu-id="95706-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="95706-107">乘數： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="95706-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="idxterm--int"></a><span data-ttu-id="95706-108">idxTerm： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95706-108">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="95706-109">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="95706-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>





## <a name="output--generatorindex"></a><span data-ttu-id="95706-110">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="95706-110">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>



## <a name="remarks"></a><span data-ttu-id="95706-111">備註</span><span class="sxs-lookup"><span data-stu-id="95706-111">Remarks</span></span>

<span data-ttu-id="95706-112">這是中繼步驟，不應該呼叫。</span><span class="sxs-lookup"><span data-stu-id="95706-112">This is an intermediate step and should not be called.</span></span>