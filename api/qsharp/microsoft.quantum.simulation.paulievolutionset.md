---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 89c81aca4cfad6087d764ac8f5a0f1426e905e4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700159"
---
# <a name="paulievolutionset-function"></a><span data-ttu-id="99a59-102">PauliEvolutionSet 函式</span><span class="sxs-lookup"><span data-stu-id="99a59-102">PauliEvolutionSet function</span></span>

<span data-ttu-id="99a59-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="99a59-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="99a59-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99a59-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99a59-105">將 dynamical 產生器表示為一組 simulatable 閘道，並以 Pauli 為基礎進行擴充。</span><span class="sxs-lookup"><span data-stu-id="99a59-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="99a59-106">輸出： [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="99a59-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="99a59-107">將 `EvolutionSet` `GeneratorIndex` Pauli 基礎對應至 ' EvolutionUnitary 的。</span><span class="sxs-lookup"><span data-stu-id="99a59-107">An `EvolutionSet` that maps a `GeneratorIndex` for the Pauli basis to an \`EvolutionUnitary.</span></span>

## <a name="remarks"></a><span data-ttu-id="99a59-108">備註</span><span class="sxs-lookup"><span data-stu-id="99a59-108">Remarks</span></span>

<span data-ttu-id="99a59-109">這是由的部分應用程式所取得 <xref:microsoft.quantum.simulation.paulievolutionfunction> 。</span><span class="sxs-lookup"><span data-stu-id="99a59-109">This is obtained by partial application of <xref:microsoft.quantum.simulation.paulievolutionfunction>.</span></span>