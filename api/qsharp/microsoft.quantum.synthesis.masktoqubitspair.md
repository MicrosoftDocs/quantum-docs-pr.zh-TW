---
uid: Microsoft.Quantum.Synthesis.MaskToQubitsPair
title: MaskToQubitsPair 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MaskToQubitsPair
qsharp.summary: Transform mask of control and target bits to a pair of control qubits and target qubits
ms.openlocfilehash: 493949b7e9f449ee6d5fca7c9f76ec4b2b0c37a3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203005"
---
# <a name="masktoqubitspair-function"></a><span data-ttu-id="04c33-102">MaskToQubitsPair 函式</span><span class="sxs-lookup"><span data-stu-id="04c33-102">MaskToQubitsPair function</span></span>

<span data-ttu-id="04c33-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="04c33-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="04c33-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04c33-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04c33-105">將控制項的遮罩和目標位轉換成一對控制項量子位和目標量子位</span><span class="sxs-lookup"><span data-stu-id="04c33-105">Transform mask of control and target bits to a pair of control qubits and target qubits</span></span>

```qsharp
function MaskToQubitsPair (qubits : Qubit[], mask : Microsoft.Quantum.Synthesis.MCMTMask) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="04c33-106">輸入</span><span class="sxs-lookup"><span data-stu-id="04c33-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="04c33-107">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="04c33-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="mask--mcmtmask"></a><span data-ttu-id="04c33-108">mask： [MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)</span><span class="sxs-lookup"><span data-stu-id="04c33-108">mask : [MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)</span></span>





## <a name="output--qubitqubit"></a><span data-ttu-id="04c33-109">Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) </span><span class="sxs-lookup"><span data-stu-id="04c33-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

