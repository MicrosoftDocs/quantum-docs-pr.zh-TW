---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 835c7a9edb22b4be630ebfc04587c12b3ff668b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829223"
---
# <a name="dumpregister-function"></a><span data-ttu-id="bbb11-102">DumpRegister 函式</span><span class="sxs-lookup"><span data-stu-id="bbb11-102">DumpRegister function</span></span>

<span data-ttu-id="bbb11-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="bbb11-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="bbb11-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bbb11-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bbb11-105">傾印目前目的電腦與指定量子位相關聯的狀態。</span><span class="sxs-lookup"><span data-stu-id="bbb11-105">Dumps the current target machine's status associated with the given qubits.</span></span>

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="bbb11-106">輸入</span><span class="sxs-lookup"><span data-stu-id="bbb11-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="bbb11-107">位置： t</span><span class="sxs-lookup"><span data-stu-id="bbb11-107">location : 'T</span></span>

<span data-ttu-id="bbb11-108">提供有關何處可以產生狀態傾印的資訊。</span><span class="sxs-lookup"><span data-stu-id="bbb11-108">Provides information on where to generate the state's dump.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="bbb11-109">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bbb11-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bbb11-110">要報告的量子位清單。</span><span class="sxs-lookup"><span data-stu-id="bbb11-110">The list of qubits to report.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bbb11-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bbb11-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="bbb11-112">無。</span><span class="sxs-lookup"><span data-stu-id="bbb11-112">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bbb11-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="bbb11-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bbb11-114">不要</span><span class="sxs-lookup"><span data-stu-id="bbb11-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="bbb11-115">備註</span><span class="sxs-lookup"><span data-stu-id="bbb11-115">Remarks</span></span>

<span data-ttu-id="bbb11-116">這個方法可讓您將與指定量子位狀態相關聯的資訊傾印到檔案或其他位置。</span><span class="sxs-lookup"><span data-stu-id="bbb11-116">This method allows you to dump the information associated with the state of the given qubits into a file or some other location.</span></span>
<span data-ttu-id="bbb11-117">實際產生的資訊和的語義 `location` 都是每個目的電腦的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="bbb11-117">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="bbb11-118">不過，將空的元組提供為位置 (`()`) 通常表示要產生主控台的輸出。</span><span class="sxs-lookup"><span data-stu-id="bbb11-118">However, providing an empty tuple as a location (`()`) typically means to generate the output to the console.</span></span>

<span data-ttu-id="bbb11-119">對於分散為量子開發工具組一部分的本機完整狀態模擬器，這個方法預期會有檔案路徑的字串，而檔案的路徑將會寫入指定的量子位的狀態 (亦即，對應子系統的 wave 函數) 為複數的一維陣列，其中每個專案都代表測量相對應狀態之機率的 amplitudes。</span><span class="sxs-lookup"><span data-stu-id="bbb11-119">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the state of the given qubits (i.e. the wave function of the corresponding  subsystem) as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
<span data-ttu-id="bbb11-120">如果指定的量子位是以其他量子位纏結，而且其狀態無法分隔，它只會報告量子位為纏結。</span><span class="sxs-lookup"><span data-stu-id="bbb11-120">If the given qubits are entangled with some other qubit and their state can't be separated, it just reports that the qubits are entangled.</span></span>