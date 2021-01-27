---
uid: Microsoft.Quantum.Simulation._MultiplyGeneratorSystem
title: _MultiplyGeneratorSystem 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 237d10a2683c8e26c81eb546b971930d1d7aee15
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857967"
---
# <a name="_multiplygeneratorsystem-function"></a><span data-ttu-id="64469-102">_MultiplyGeneratorSystem 函式</span><span class="sxs-lookup"><span data-stu-id="64469-102">_MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="64469-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="64469-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="64469-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64469-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64469-105">將中所有詞彙的係數相乘 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="64469-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function _MultiplyGeneratorSystem (multiplier : Double, idxTerm : Int, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="64469-106">輸入</span><span class="sxs-lookup"><span data-stu-id="64469-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="64469-107">乘數： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="64469-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="idxterm--int"></a><span data-ttu-id="64469-108">idxTerm： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="64469-108">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="64469-109">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="64469-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>





## <a name="output--generatorindex"></a><span data-ttu-id="64469-110">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="64469-110">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>



## <a name="remarks"></a><span data-ttu-id="64469-111">備註</span><span class="sxs-lookup"><span data-stu-id="64469-111">Remarks</span></span>

<span data-ttu-id="64469-112">這是中繼步驟，不應該呼叫。</span><span class="sxs-lookup"><span data-stu-id="64469-112">This is an intermediate step and should not be called.</span></span>