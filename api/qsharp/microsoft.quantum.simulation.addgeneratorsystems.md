---
uid: Microsoft.Quantum.Simulation.AddGeneratorSystems
title: AddGeneratorSystems 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: b23fc89b941a7cdd93ee7938dda50eb14e3ed528
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857944"
---
# <a name="addgeneratorsystems-function"></a><span data-ttu-id="c2df1-102">AddGeneratorSystems 函式</span><span class="sxs-lookup"><span data-stu-id="c2df1-102">AddGeneratorSystems function</span></span>

<span data-ttu-id="c2df1-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c2df1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c2df1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2df1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2df1-105">新增兩個 `GeneratorSystem` 來建立新的 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="c2df1-105">Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.</span></span>

```qsharp
function AddGeneratorSystems (generatorSystemA : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemB : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="c2df1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c2df1-106">Input</span></span>

### <a name="generatorsystema--generatorsystem"></a><span data-ttu-id="c2df1-107">generatorSystemA： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="c2df1-107">generatorSystemA : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="c2df1-108">第一個 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="c2df1-108">The first `GeneratorSystem`.</span></span>


### <a name="generatorsystemb--generatorsystem"></a><span data-ttu-id="c2df1-109">generatorSystemB： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="c2df1-109">generatorSystemB : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="c2df1-110">第二個 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="c2df1-110">The second `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="c2df1-111">輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="c2df1-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="c2df1-112">`GeneratorSystem`代表系統的，這是輸入產生器系統的總和。</span><span class="sxs-lookup"><span data-stu-id="c2df1-112">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2df1-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c2df1-113">See Also</span></span>

- [<span data-ttu-id="c2df1-114">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="c2df1-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)