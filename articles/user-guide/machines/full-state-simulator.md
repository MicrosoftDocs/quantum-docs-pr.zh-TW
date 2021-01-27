---
title: 完整狀態量子模擬器-量子開發工具組
description: 瞭解如何 Q# 在 Microsoft 量子開發工具組的完整狀態模擬器上執行您的程式。
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 950e61c812cc6df739ddaa1de855f753557d6d1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858179"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="24e4a-103">量子開發工具組 (QDK) 完整狀態模擬器</span><span class="sxs-lookup"><span data-stu-id="24e4a-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="24e4a-104">QDK 會提供在本機電腦上模擬量子機器的完整狀態模擬器。</span><span class="sxs-lookup"><span data-stu-id="24e4a-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="24e4a-105">您可以使用完整狀態模擬器來執行和偵測以撰寫的量子演算法 Q# ，最多可利用30量子位。</span><span class="sxs-lookup"><span data-stu-id="24e4a-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="24e4a-106">完整狀態模擬器類似于 Microsoft Research  [LIQ $ Ui | \rangle $](http://stationq.github.io/Liquid/) platform 中所使用的量子模擬器。</span><span class="sxs-lookup"><span data-stu-id="24e4a-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="24e4a-107">叫用和執行完整狀態模擬器</span><span class="sxs-lookup"><span data-stu-id="24e4a-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="24e4a-108">您可以透過類別公開完整狀態模擬器 `QuantumSimulator` 。</span><span class="sxs-lookup"><span data-stu-id="24e4a-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="24e4a-109">如需其他詳細資訊，請參閱 [執行 Q# 程式的方法](xref:microsoft.quantum.guide.host-programs)。</span><span class="sxs-lookup"><span data-stu-id="24e4a-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="24e4a-110">從 C 叫用模擬器#</span><span class="sxs-lookup"><span data-stu-id="24e4a-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="24e4a-111">建立類別的實例， `QuantumSimulator` 然後將它傳遞給量子作業的 `Run` 方法，以及任何其他參數。</span><span class="sxs-lookup"><span data-stu-id="24e4a-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="24e4a-112">由於類別會實 `QuantumSimulator` 作為 <xref:System.IDisposable> 介面，因此當您不再需要模擬器的實例時，您必須呼叫 `Dispose` 方法。</span><span class="sxs-lookup"><span data-stu-id="24e4a-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="24e4a-113">若要這麼做，最好的方法就是在 [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) 語句內包裝模擬器宣告和作業，這會自動呼叫 `Dispose` 方法。</span><span class="sxs-lookup"><span data-stu-id="24e4a-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="24e4a-114">從 Python 叫用模擬器</span><span class="sxs-lookup"><span data-stu-id="24e4a-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="24e4a-115">使用已匯入作業的 Python 程式庫中的 [模擬 ( # B1 ](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) 方法 Q# Q# ：</span><span class="sxs-lookup"><span data-stu-id="24e4a-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="24e4a-116">從命令列叫用模擬器</span><span class="sxs-lookup"><span data-stu-id="24e4a-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="24e4a-117">Q#從命令列執行程式時，完整狀態模擬器是預設的目的電腦。</span><span class="sxs-lookup"><span data-stu-id="24e4a-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="24e4a-118">（選擇性）您可以使用 **--** 模擬器 (或 **-s** 快速鍵) 參數來指定所需的目的電腦。</span><span class="sxs-lookup"><span data-stu-id="24e4a-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="24e4a-119">下列兩個命令都會使用完整狀態模擬器來執行程式。</span><span class="sxs-lookup"><span data-stu-id="24e4a-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="24e4a-120">從 Juptyer 筆記本叫用模擬器</span><span class="sxs-lookup"><span data-stu-id="24e4a-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="24e4a-121">使用 I Q# 魔術命令 [% 模擬](xref:microsoft.quantum.iqsharp.magic-ref.simulate) 來執行 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="24e4a-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="24e4a-122">植入模擬器</span><span class="sxs-lookup"><span data-stu-id="24e4a-122">Seeding the simulator</span></span>

<span data-ttu-id="24e4a-123">根據預設，完整狀態模擬器會使用亂數產生器來模擬量子隨機性。</span><span class="sxs-lookup"><span data-stu-id="24e4a-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="24e4a-124">基於測試目的，有決定性的結果有時會很有用。</span><span class="sxs-lookup"><span data-stu-id="24e4a-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="24e4a-125">在 c # 程式中，您可以透過參數在函式中提供亂數產生器的種子來完成這項操作 `QuantumSimulator` `randomNumberGeneratorSeed` 。</span><span class="sxs-lookup"><span data-stu-id="24e4a-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="24e4a-126">設定執行緒</span><span class="sxs-lookup"><span data-stu-id="24e4a-126">Configuring threads</span></span>

<span data-ttu-id="24e4a-127">完整狀態模擬器會使用 [OpenMP](http://www.openmp.org/) 將所需的線性代數平行化。</span><span class="sxs-lookup"><span data-stu-id="24e4a-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="24e4a-128">根據預設，OpenMP 會使用所有可用的硬體執行緒，這表示具有少量量子位的程式通常執行速度很慢，因為所需的協調 dwarfs 實際工作。</span><span class="sxs-lookup"><span data-stu-id="24e4a-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="24e4a-129">您可以藉由將環境變數設定 `OMP_NUM_THREADS` 為較小的數位來修正此問題。</span><span class="sxs-lookup"><span data-stu-id="24e4a-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="24e4a-130">根據經驗法則，請針對最多四個量子位設定一個執行緒，然後針對每個量子位設定一個額外的執行緒。</span><span class="sxs-lookup"><span data-stu-id="24e4a-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="24e4a-131">您可能需要根據您的演算法調整變數。</span><span class="sxs-lookup"><span data-stu-id="24e4a-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="24e4a-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="24e4a-132">See also</span></span>

- [<span data-ttu-id="24e4a-133">量子資源估算器</span><span class="sxs-lookup"><span data-stu-id="24e4a-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="24e4a-134">量子 Toffoli 模擬器</span><span class="sxs-lookup"><span data-stu-id="24e4a-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="24e4a-135">量子追蹤模擬器</span><span class="sxs-lookup"><span data-stu-id="24e4a-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)