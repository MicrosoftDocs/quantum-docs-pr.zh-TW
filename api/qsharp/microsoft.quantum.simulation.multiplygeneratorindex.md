---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: b53a483a0c2b8c99b733c9c87289fb212b5ffc89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848022"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="56751-102">MultiplyGeneratorIndex 函式</span><span class="sxs-lookup"><span data-stu-id="56751-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="56751-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="56751-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="56751-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56751-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56751-105">將中的係數相乘 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="56751-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="56751-106">輸入</span><span class="sxs-lookup"><span data-stu-id="56751-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="56751-107">乘數： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="56751-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="56751-108">係數上的乘數。</span><span class="sxs-lookup"><span data-stu-id="56751-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="56751-109">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="56751-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="56751-110">要相乘的 `GeneratorIndex`。</span><span class="sxs-lookup"><span data-stu-id="56751-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="56751-111">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="56751-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="56751-112">， `GeneratorIndex` 表示具有較大係數的詞彙 `multiplier` 。</span><span class="sxs-lookup"><span data-stu-id="56751-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="example"></a><span data-ttu-id="56751-113">範例</span><span class="sxs-lookup"><span data-stu-id="56751-113">Example</span></span>

```qsharp
let gen = GeneratorIndex(([1,2,3],[coeff]),[1,2,3]);
let ((idxPaulis, idxDoubles), idxQubits) = MultiplyGeneratorIndex(multiplier, gen);
// idxDoubles[0] == multiplier * coeff;
```

## <a name="see-also"></a><span data-ttu-id="56751-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="56751-114">See Also</span></span>

- [<span data-ttu-id="56751-115">GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="56751-115">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)