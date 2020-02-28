---
title: 完整狀態模擬器
description: '瞭解如何在 Microsoft Quantum Development Kit 完整狀態模擬器上執行您的 Q # 程式。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906112"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="7347d-103">量子開發工具組完整狀態模擬器</span><span class="sxs-lookup"><span data-stu-id="7347d-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="7347d-104">配量開發工具組提供的完整狀態配量模擬器，類似于 Microsoft Research 的[LIQ $ Ui | \rangle $](http://stationq.github.io/Liquid/) 。</span><span class="sxs-lookup"><span data-stu-id="7347d-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="7347d-105">此模擬器可用來執行和偵錯工具中以 Q # 撰寫的量子演算法。</span><span class="sxs-lookup"><span data-stu-id="7347d-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="7347d-106">這個量子模擬器會透過 `QuantumSimulator` 類別公開。</span><span class="sxs-lookup"><span data-stu-id="7347d-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="7347d-107">若要使用模擬器，請直接建立此類別的實例，並將它傳遞給您想要執行之量子作業的 `Run` 方法，以及其餘的參數：</span><span class="sxs-lookup"><span data-stu-id="7347d-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="7347d-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="7347d-108">IDisposable</span></span>

<span data-ttu-id="7347d-109">`QuantumSimulator` 類別會執行 <xref:System.IDisposable>，因此一旦模擬器的實例不再使用，就應該呼叫 `Dispose` 方法。</span><span class="sxs-lookup"><span data-stu-id="7347d-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="7347d-110">執行這項操作的最佳方式是將模擬器包裝在 `using` 語句中，如上述範例所示。</span><span class="sxs-lookup"><span data-stu-id="7347d-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="7347d-111">Seed</span><span class="sxs-lookup"><span data-stu-id="7347d-111">Seed</span></span>

<span data-ttu-id="7347d-112">`QuantumSimulator` 使用亂數產生器來模擬量子隨機性。</span><span class="sxs-lookup"><span data-stu-id="7347d-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="7347d-113">基於測試目的，有決定性的結果有時會很有用。</span><span class="sxs-lookup"><span data-stu-id="7347d-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="7347d-114">這可以藉由在 `QuantumSimulator`的程式碼中透過 `randomNumberGeneratorSeed` 參數提供亂數產生器的種子來完成：</span><span class="sxs-lookup"><span data-stu-id="7347d-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="7347d-115">Threads</span><span class="sxs-lookup"><span data-stu-id="7347d-115">Threads</span></span>

<span data-ttu-id="7347d-116">`QuantumSimulator` 使用[OpenMP](http://www.openmp.org/)來平行處理所需的線性代數。</span><span class="sxs-lookup"><span data-stu-id="7347d-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="7347d-117">根據預設，OpenMP 會使用所有可用的硬體執行緒，這表示具有少量量子位元的程式常會執行緩慢，因為所需的協調會阻礙實際的工作。</span><span class="sxs-lookup"><span data-stu-id="7347d-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="7347d-118">將環境變數 `OMP_NUM_THREADS` 設定為較小的數位，即可修正此問題。</span><span class="sxs-lookup"><span data-stu-id="7347d-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="7347d-119">一個非常粗略的經驗法則是，1 個執行緒最多可用於 4 個量子位元，而其後的每個量子位元則應使用一個額外的執行緒，但這主要取決於您的演算法。</span><span class="sxs-lookup"><span data-stu-id="7347d-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

