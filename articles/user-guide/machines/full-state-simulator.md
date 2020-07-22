---
title: 完整狀態量子模擬器-量子開發工具組
description: '瞭解如何在 Microsoft Quantum Development Kit 完整狀態模擬器上執行您的 Q # 程式。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: 563fdbd2a45461d112e4c46651eddd75c6fc3db2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871173"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="9de70-103">量子開發工具組（QDK）完整狀態模擬器</span><span class="sxs-lookup"><span data-stu-id="9de70-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="9de70-104">QDK 提供的完整狀態模擬器會模擬您本機電腦上的量子機器。</span><span class="sxs-lookup"><span data-stu-id="9de70-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="9de70-105">您可以使用完整狀態模擬器來執行和調試以 Q # 撰寫的配量演算法，最多可達 30 qubits。</span><span class="sxs-lookup"><span data-stu-id="9de70-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="9de70-106">完整狀態模擬器類似于 Microsoft Research 的[LIQ $ Ui | \rangle $](http://stationq.github.io/Liquid/) platform 中使用的量子模擬器。</span><span class="sxs-lookup"><span data-stu-id="9de70-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="9de70-107">叫用和執行完整狀態模擬器</span><span class="sxs-lookup"><span data-stu-id="9de70-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="9de70-108">您可以透過類別公開完整狀態模擬器 `QuantumSimulator` 。</span><span class="sxs-lookup"><span data-stu-id="9de70-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="9de70-109">如需其他詳細資訊，請參閱[執行 Q # 程式的方式](xref:microsoft.quantum.guide.host-programs)。</span><span class="sxs-lookup"><span data-stu-id="9de70-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="9de70-110">從 C 叫用模擬器#</span><span class="sxs-lookup"><span data-stu-id="9de70-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="9de70-111">建立類別的實例， `QuantumSimulator` 然後將它傳遞給量子作業的 `Run` 方法，以及任何其他參數。</span><span class="sxs-lookup"><span data-stu-id="9de70-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="9de70-112">因為類別會實 `QuantumSimulator` <xref:System.IDisposable> 作用介面，所以您必須在不再需要模擬器的 `Dispose` 實例後呼叫方法。</span><span class="sxs-lookup"><span data-stu-id="9de70-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="9de70-113">這麼做的最佳方式是在[using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement)語句中包裝模擬器宣告和作業，這會自動呼叫 `Dispose` 方法。</span><span class="sxs-lookup"><span data-stu-id="9de70-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="9de70-114">從 Python 叫用模擬器</span><span class="sxs-lookup"><span data-stu-id="9de70-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="9de70-115">使用來自 Q # Python 程式庫的[模擬（）](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable)方法，以及匯入的 Q # 操作：</span><span class="sxs-lookup"><span data-stu-id="9de70-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="9de70-116">從命令列叫用模擬器</span><span class="sxs-lookup"><span data-stu-id="9de70-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="9de70-117">從命令列執行 Q # 程式時，完整狀態模擬器是預設的目的電腦。</span><span class="sxs-lookup"><span data-stu-id="9de70-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="9de70-118">（選擇性）您可以使用 **--** 模擬器（或 **-s**快捷方式）參數來指定所需的目的電腦。</span><span class="sxs-lookup"><span data-stu-id="9de70-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="9de70-119">下列兩個命令都會使用完整狀態模擬器來執行程式。</span><span class="sxs-lookup"><span data-stu-id="9de70-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="9de70-120">從 Juptyer 筆記本叫用模擬器</span><span class="sxs-lookup"><span data-stu-id="9de70-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="9de70-121">使用 IQ # 魔術命令[% 模擬](xref:microsoft.quantum.iqsharp.magic-ref.simulate)來執行 Q # 作業。</span><span class="sxs-lookup"><span data-stu-id="9de70-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="9de70-122">植入模擬器</span><span class="sxs-lookup"><span data-stu-id="9de70-122">Seeding the simulator</span></span>

<span data-ttu-id="9de70-123">根據預設，完整狀態模擬器會使用亂數產生器來模擬量子隨機性。</span><span class="sxs-lookup"><span data-stu-id="9de70-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="9de70-124">基於測試目的，有決定性的結果有時會很有用。</span><span class="sxs-lookup"><span data-stu-id="9de70-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="9de70-125">在 c # 程式中，您可以藉由在函式中透過參數提供亂數字產生器的種子來完成這項操作 `QuantumSimulator` `randomNumberGeneratorSeed` 。</span><span class="sxs-lookup"><span data-stu-id="9de70-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="9de70-126">設定執行緒</span><span class="sxs-lookup"><span data-stu-id="9de70-126">Configuring threads</span></span>

<span data-ttu-id="9de70-127">完整狀態模擬器會使用[OpenMP](http://www.openmp.org/)來平行處理所需的線性代數。</span><span class="sxs-lookup"><span data-stu-id="9de70-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="9de70-128">根據預設，OpenMP 會使用所有可用的硬體執行緒，這表示具有少量 qubits 的程式通常會執行緩慢，因為所需的協調會 dwarfs 實際的工作。</span><span class="sxs-lookup"><span data-stu-id="9de70-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="9de70-129">您可以藉由將環境變數設定 `OMP_NUM_THREADS` 為較小的數位來修正此問題。</span><span class="sxs-lookup"><span data-stu-id="9de70-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="9de70-130">根據經驗法則，將一個執行緒設定為最多四個 qubits，然後針對每個 qubit 設定一個額外的執行緒。</span><span class="sxs-lookup"><span data-stu-id="9de70-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="9de70-131">視您的演算法而定，您可能需要調整變數。</span><span class="sxs-lookup"><span data-stu-id="9de70-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="9de70-132">請參閱</span><span class="sxs-lookup"><span data-stu-id="9de70-132">See also</span></span>

- [<span data-ttu-id="9de70-133">量子資源估計工具</span><span class="sxs-lookup"><span data-stu-id="9de70-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="9de70-134">量子 Toffoli 模擬器</span><span class="sxs-lookup"><span data-stu-id="9de70-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="9de70-135">量子追蹤模擬器</span><span class="sxs-lookup"><span data-stu-id="9de70-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)