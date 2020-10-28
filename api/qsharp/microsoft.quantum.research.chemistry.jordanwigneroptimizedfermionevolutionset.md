---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: JordanWignerOptimizedFermionEvolutionSet 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: d2d916655b7538b39d5739d67dbb3fc9920cf67a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700186"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a><span data-ttu-id="71973-102">JordanWignerOptimizedFermionEvolutionSet 函式</span><span class="sxs-lookup"><span data-stu-id="71973-102">JordanWignerOptimizedFermionEvolutionSet function</span></span>

<span data-ttu-id="71973-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="71973-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="71973-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71973-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71973-105">將 dynamical 產生器表示為一組 simulatable 閘道，並以 Pauli 為基礎進行擴充。</span><span class="sxs-lookup"><span data-stu-id="71973-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a><span data-ttu-id="71973-106">輸入</span><span class="sxs-lookup"><span data-stu-id="71973-106">Input</span></span>

### <a name="parityqubit--qubit"></a><span data-ttu-id="71973-107">parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="71973-107">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="71973-108">量子位，決定時間演進的正負號。</span><span class="sxs-lookup"><span data-stu-id="71973-108">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionset"></a><span data-ttu-id="71973-109">輸出： [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="71973-109">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="71973-110">將 `EvolutionSet` `GeneratorIndex` JWOptimized 基礎對應至 ' EvolutionUnitary 的。</span><span class="sxs-lookup"><span data-stu-id="71973-110">An `EvolutionSet` that maps a `GeneratorIndex` for the JWOptimized basis to an \`EvolutionUnitary.</span></span>