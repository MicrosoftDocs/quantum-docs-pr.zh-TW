---
title: 量子開發工具組 Toffoli 模擬器
description: 深入瞭解 Microsoft QDK Toffoli 模擬器，這是一種特殊用途的量子模擬器，可與數百萬個 qubits 搭配使用。
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907013"
---
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="18d04-103">量子開發工具組 Toffoli 模擬器</span><span class="sxs-lookup"><span data-stu-id="18d04-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="18d04-104">配量開發工具組提供 Toffoli 模擬器，這是一種特殊用途的模擬器，可以模擬僅限於 X、CNOT-CONTAINS 和多重控制 X 配量作業的配量演算法（所有傳統邏輯和計算皆可使用）。</span><span class="sxs-lookup"><span data-stu-id="18d04-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="18d04-105">雖然 Toffoli 模擬器比[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器更受限制，但它可以模擬遠較多的 qubits。</span><span class="sxs-lookup"><span data-stu-id="18d04-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="18d04-106">Toffoli 模擬器可以與數百萬個 qubits 搭配使用，而完整狀態模擬器通常限制為大約30個。</span><span class="sxs-lookup"><span data-stu-id="18d04-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="18d04-107">它可以執行並在您的電腦上，以 Q # 撰寫一組有限的量子演算法，比方說，評估布耳函數的 oracles 可以使用這些閘道來執行，因此在上測試時，會使用此模擬器來改變大量的 qubits。</span><span class="sxs-lookup"><span data-stu-id="18d04-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="18d04-108">這個量子模擬器會透過 `ToffoliSimulator` 類別公開。</span><span class="sxs-lookup"><span data-stu-id="18d04-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="18d04-109">若要使用模擬器，請直接建立此類別的實例，並將它傳遞給您想要執行之量子作業的 `Run` 方法，以及其餘的參數：</span><span class="sxs-lookup"><span data-stu-id="18d04-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="18d04-110">其他作業</span><span class="sxs-lookup"><span data-stu-id="18d04-110">Other Operations</span></span>

<span data-ttu-id="18d04-111">當產生的作業等於 `X` 或身分識別時，`ToffoliSimulator` 支援旋轉和 exponentiated Paulis，例如 `R` 和 `Exp`。</span><span class="sxs-lookup"><span data-stu-id="18d04-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="18d04-112">測量和判斷提示受到支援，但僅限在 Pauli `Z` 基礎中。</span><span class="sxs-lookup"><span data-stu-id="18d04-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="18d04-113">請注意，某些測量的機率一律為0或 1;Toffoli 模擬器中沒有隨機性。</span><span class="sxs-lookup"><span data-stu-id="18d04-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="18d04-114">支援 `DumpMachine` 和 `DumpRegister`。</span><span class="sxs-lookup"><span data-stu-id="18d04-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="18d04-115">它們都會輸出每個 qubit 的目前 `Z`基礎狀態，每行一個 qubit。</span><span class="sxs-lookup"><span data-stu-id="18d04-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="18d04-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="18d04-116">QubitCount</span></span>

<span data-ttu-id="18d04-117">根據預設，`ToffoliSimulator` 會為 65536 qubits 配置空間。</span><span class="sxs-lookup"><span data-stu-id="18d04-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="18d04-118">如果您的演算法需要的不只是這種情況，您可以藉由將 `qubitCount` 參數的值提供給此函式來變更 qubit 計數。</span><span class="sxs-lookup"><span data-stu-id="18d04-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="18d04-119">每個額外的 qubit 都需要額外的記憶體位元組，因此高估您需要的 qubits 數目並不會有重大成本。</span><span class="sxs-lookup"><span data-stu-id="18d04-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="18d04-120">例如：</span><span class="sxs-lookup"><span data-stu-id="18d04-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
