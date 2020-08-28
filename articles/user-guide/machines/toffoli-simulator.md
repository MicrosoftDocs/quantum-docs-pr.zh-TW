---
title: 量子 Toffoli 模擬器-量子開發工具組
description: 深入瞭解 Microsoft QDK Toffoli 模擬器，這是可用於數百萬個量子位的特殊用途量子模擬器。
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6a0885035c12a99ae43533f04cdc95c5c529380a
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992202"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="8e756-103">量子開發工具組 (QDK) Toffoli 模擬器</span><span class="sxs-lookup"><span data-stu-id="8e756-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="8e756-104">QDK Toffoli 模擬器是具有有限範圍的特殊用途模擬器，而且僅支援 `X` 、 `CNOT` 和多重控制的 `X` 量子作業。</span><span class="sxs-lookup"><span data-stu-id="8e756-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="8e756-105">所有傳統邏輯和計算都可供使用。</span><span class="sxs-lookup"><span data-stu-id="8e756-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="8e756-106">雖然 Toffoli 模擬器的功能比 [完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器更受限制，但是它的優點是能夠模擬更多量子位。</span><span class="sxs-lookup"><span data-stu-id="8e756-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="8e756-107">Toffoli 模擬器可用於數百萬個量子位，而完整狀態模擬器的限制為大約30個量子位。</span><span class="sxs-lookup"><span data-stu-id="8e756-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="8e756-108">這項功能很有用，例如，使用評估布林函式的 oracle 時，可以使用有限的支援演算法集來執行，並在大量的量子位上進行測試。</span><span class="sxs-lookup"><span data-stu-id="8e756-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="8e756-109">叫用 Toffoli 模擬器</span><span class="sxs-lookup"><span data-stu-id="8e756-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="8e756-110">您可以透過類別公開 Toffoli 模擬器 `ToffoliSimulator` 。</span><span class="sxs-lookup"><span data-stu-id="8e756-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="8e756-111">如需其他詳細資訊，請參閱 [執行 Q# 程式的方法](xref:microsoft.quantum.guide.host-programs)。</span><span class="sxs-lookup"><span data-stu-id="8e756-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="8e756-112">從 C 叫用 Toffoli 模擬器#</span><span class="sxs-lookup"><span data-stu-id="8e756-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="8e756-113">就像其他目標機器一樣，您必須先建立 `ToffoliSimulator` 類別的執行個體，然後將其當做作業中 `Run` 方法的第一個參數傳遞。</span><span class="sxs-lookup"><span data-stu-id="8e756-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="8e756-114">請注意，不同於 `QuantumSimulator` 類別，`ToffoliSimulator` 類別不會實作 <xref:System.IDisposable> 介面，因此您不需要將其放在 `using` 陳述式內。</span><span class="sxs-lookup"><span data-stu-id="8e756-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="8e756-115">從 Python 叫用 Toffoli 模擬器</span><span class="sxs-lookup"><span data-stu-id="8e756-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="8e756-116">使用匯入作業，從 Python 程式庫使用 [toffoli_simulate ( # B1 ](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) 方法 Q# ：</span><span class="sxs-lookup"><span data-stu-id="8e756-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="8e756-117">從命令列叫用 Toffoli 模擬器</span><span class="sxs-lookup"><span data-stu-id="8e756-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="8e756-118">Q#從命令列執行程式時，請使用 **--** 模擬器 (或 **-s**快速鍵) 參數來指定 Toffoli 模擬器目的電腦。</span><span class="sxs-lookup"><span data-stu-id="8e756-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="8e756-119">下列命令會使用資源估算器來執行程式：</span><span class="sxs-lookup"><span data-stu-id="8e756-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="8e756-120">從 Juptyer 筆記本叫用 Toffoli 模擬器</span><span class="sxs-lookup"><span data-stu-id="8e756-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="8e756-121">使用 I Q# 魔術命令 [% toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) 來執行 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="8e756-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="8e756-122">支援的作業</span><span class="sxs-lookup"><span data-stu-id="8e756-122">Supported operations</span></span>

<span data-ttu-id="8e756-123">Toffoli 模擬器支援：</span><span class="sxs-lookup"><span data-stu-id="8e756-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="8e756-124">`R` `Exp` 當產生的作業等於或識別矩陣時，旋轉和 exponentiated Paulis （例如和） `X` 。</span><span class="sxs-lookup"><span data-stu-id="8e756-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="8e756-125">量測 [和判斷提示作業，但](xref:microsoft.quantum.diagnostics.assertmeasurement) 僅限 Pauli `Z` 基礎。</span><span class="sxs-lookup"><span data-stu-id="8e756-125">Measurement and [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="8e756-126">請注意，測量運算的機率一律為 **0** 或 **1**;Toffoli 模擬器中沒有隨機性。</span><span class="sxs-lookup"><span data-stu-id="8e756-126">Note that a measurement operation's probability is always either **0** or **1**; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="8e756-127">`DumpMachine` 和函式 `DumpRegister` 。</span><span class="sxs-lookup"><span data-stu-id="8e756-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="8e756-128">這兩個函式都會輸出 `Z` 每個量子位的目前基礎狀態，每行一個量子位。</span><span class="sxs-lookup"><span data-stu-id="8e756-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="8e756-129">指定量子位的數目</span><span class="sxs-lookup"><span data-stu-id="8e756-129">Specifying the number of qubits</span></span>

<span data-ttu-id="8e756-130">根據預設， `ToffoliSimulator` 實例會為65536量子位配置空間。</span><span class="sxs-lookup"><span data-stu-id="8e756-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="8e756-131">如果您的演算法需要比這個更多的量子位，您可以提供參數的值給函式來指定量子位元數目 `qubitCount` 。</span><span class="sxs-lookup"><span data-stu-id="8e756-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="8e756-132">每個額外的量子位都只需要一個位元組的記憶體，因此高估您需要的量子位數量沒有任何重大成本。</span><span class="sxs-lookup"><span data-stu-id="8e756-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="8e756-133">例如：</span><span class="sxs-lookup"><span data-stu-id="8e756-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="8e756-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8e756-134">See also</span></span>

- [<span data-ttu-id="8e756-135">量子資源估算器</span><span class="sxs-lookup"><span data-stu-id="8e756-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="8e756-136">量子追蹤模擬器</span><span class="sxs-lookup"><span data-stu-id="8e756-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="8e756-137">量子完整狀態模擬器</span><span class="sxs-lookup"><span data-stu-id="8e756-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 