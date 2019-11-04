---
title: Quantum Development Kit Full State Simulator | Microsoft Docs
description: Overview of Microsoft's Quantum Development Kit Full State Simulator
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184673"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="bdf73-103">Quantum Development Kit Full State Simulator</span><span class="sxs-lookup"><span data-stu-id="bdf73-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="bdf73-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="bdf73-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="bdf73-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span><span class="sxs-lookup"><span data-stu-id="bdf73-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="bdf73-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span><span class="sxs-lookup"><span data-stu-id="bdf73-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="bdf73-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span><span class="sxs-lookup"><span data-stu-id="bdf73-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="bdf73-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="bdf73-108">IDisposable</span></span>

<span data-ttu-id="bdf73-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span><span class="sxs-lookup"><span data-stu-id="bdf73-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="bdf73-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span><span class="sxs-lookup"><span data-stu-id="bdf73-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="bdf73-111">Seed</span><span class="sxs-lookup"><span data-stu-id="bdf73-111">Seed</span></span>

<span data-ttu-id="bdf73-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span><span class="sxs-lookup"><span data-stu-id="bdf73-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="bdf73-113">For testing purposes, it is sometimes useful to have deterministic results.</span><span class="sxs-lookup"><span data-stu-id="bdf73-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="bdf73-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span><span class="sxs-lookup"><span data-stu-id="bdf73-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="bdf73-115">Threads</span><span class="sxs-lookup"><span data-stu-id="bdf73-115">Threads</span></span>

<span data-ttu-id="bdf73-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span><span class="sxs-lookup"><span data-stu-id="bdf73-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="bdf73-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span><span class="sxs-lookup"><span data-stu-id="bdf73-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="bdf73-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span><span class="sxs-lookup"><span data-stu-id="bdf73-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="bdf73-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span><span class="sxs-lookup"><span data-stu-id="bdf73-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

