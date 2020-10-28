---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: 9ee0568073b65b027cc98eb56934e9286b59c27f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700858"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="cf7be-102">MultiplyGeneratorIndex 函式</span><span class="sxs-lookup"><span data-stu-id="cf7be-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="cf7be-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="cf7be-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="cf7be-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cf7be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cf7be-105">將中的係數相乘 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="cf7be-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="cf7be-106">輸入</span><span class="sxs-lookup"><span data-stu-id="cf7be-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="cf7be-107">乘數： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cf7be-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cf7be-108">係數上的乘數。</span><span class="sxs-lookup"><span data-stu-id="cf7be-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="cf7be-109">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="cf7be-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="cf7be-110">要相乘的 `GeneratorIndex`。</span><span class="sxs-lookup"><span data-stu-id="cf7be-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="cf7be-111">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="cf7be-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="cf7be-112">， `GeneratorIndex` 表示具有較大係數的詞彙 `multiplier` 。</span><span class="sxs-lookup"><span data-stu-id="cf7be-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf7be-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cf7be-113">See Also</span></span>

- [<span data-ttu-id="cf7be-114">GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="cf7be-114">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)