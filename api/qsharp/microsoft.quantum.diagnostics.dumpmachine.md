---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: e7eb2dfce060b61e27deae31e3c1fc6dc3d7655c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202102"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="33711-102">DumpMachine 函式</span><span class="sxs-lookup"><span data-stu-id="33711-102">DumpMachine function</span></span>

<span data-ttu-id="33711-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="33711-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="33711-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="33711-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="33711-105">傾印目前目的電腦的狀態。</span><span class="sxs-lookup"><span data-stu-id="33711-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="33711-106">輸入</span><span class="sxs-lookup"><span data-stu-id="33711-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="33711-107">位置： t</span><span class="sxs-lookup"><span data-stu-id="33711-107">location : 'T</span></span>

<span data-ttu-id="33711-108">提供有關如何產生機器傾印的資訊。</span><span class="sxs-lookup"><span data-stu-id="33711-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33711-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33711-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="33711-110">無。</span><span class="sxs-lookup"><span data-stu-id="33711-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="33711-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="33711-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="33711-112">不要</span><span class="sxs-lookup"><span data-stu-id="33711-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="33711-113">備註</span><span class="sxs-lookup"><span data-stu-id="33711-113">Remarks</span></span>

<span data-ttu-id="33711-114">這個方法可讓您將目的電腦目前狀態的相關資訊傾印到檔案或其他位置。</span><span class="sxs-lookup"><span data-stu-id="33711-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="33711-115">實際產生的資訊和的語義 `location` 都是每個目的電腦的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="33711-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="33711-116">不過，將空的元組提供為位置 (`()`) ，或只是省略 `location` 參數通常表示要產生主控台的輸出。</span><span class="sxs-lookup"><span data-stu-id="33711-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="33711-117">對於分散為量子開發工具組一部分的本機完整狀態模擬器，這個方法預期會有檔案路徑的字串，而檔案的路徑會將 wave 函式寫入為一維的複數陣列，其中每個元素都代表測量相對應狀態之機率的 amplitudes。</span><span class="sxs-lookup"><span data-stu-id="33711-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>