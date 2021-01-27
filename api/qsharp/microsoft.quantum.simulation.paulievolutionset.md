---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 961c95e6787b69e35ca531fa36164cc988ad660d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847952"
---
# <a name="paulievolutionset-function"></a><span data-ttu-id="1cfc5-102">PauliEvolutionSet 函式</span><span class="sxs-lookup"><span data-stu-id="1cfc5-102">PauliEvolutionSet function</span></span>

<span data-ttu-id="1cfc5-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1cfc5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1cfc5-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1cfc5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1cfc5-105">將 dynamical 產生器表示為一組 simulatable 閘道，並以 Pauli 為基礎進行擴充。</span><span class="sxs-lookup"><span data-stu-id="1cfc5-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="1cfc5-106">輸出： [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="1cfc5-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="1cfc5-107">將 `EvolutionSet` `GeneratorIndex` Pauli 基礎對應至 ' EvolutionUnitary 的。</span><span class="sxs-lookup"><span data-stu-id="1cfc5-107">An `EvolutionSet` that maps a `GeneratorIndex` for the Pauli basis to an \`EvolutionUnitary.</span></span>

## <a name="remarks"></a><span data-ttu-id="1cfc5-108">備註</span><span class="sxs-lookup"><span data-stu-id="1cfc5-108">Remarks</span></span>

<span data-ttu-id="1cfc5-109">這是由的部分應用程式所取得 <xref:microsoft.quantum.simulation.paulievolutionfunction> 。</span><span class="sxs-lookup"><span data-stu-id="1cfc5-109">This is obtained by partial application of <xref:microsoft.quantum.simulation.paulievolutionfunction>.</span></span>