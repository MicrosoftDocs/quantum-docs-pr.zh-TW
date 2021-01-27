---
uid: Microsoft.Quantum.Canon.SwapReverseRegister
title: SwapReverseRegister 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: SwapReverseRegister
qsharp.summary: Uses SWAP gates to Reversed the order of the qubits in a register.
ms.openlocfilehash: ca553670719c7cfff84f2eedad8cbc16189e0e98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852066"
---
# <a name="swapreverseregister-operation"></a><span data-ttu-id="28ddf-102">SwapReverseRegister 操作</span><span class="sxs-lookup"><span data-stu-id="28ddf-102">SwapReverseRegister operation</span></span>

<span data-ttu-id="28ddf-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="28ddf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="28ddf-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28ddf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28ddf-105">使用交換閘道反轉注冊中量子位的順序。</span><span class="sxs-lookup"><span data-stu-id="28ddf-105">Uses SWAP gates to Reversed the order of the qubits in a register.</span></span>

```qsharp
operation SwapReverseRegister (register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="28ddf-106">輸入</span><span class="sxs-lookup"><span data-stu-id="28ddf-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="28ddf-107">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="28ddf-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="28ddf-108">應使用交換閘道反轉的量子位順序</span><span class="sxs-lookup"><span data-stu-id="28ddf-108">The qubits order of which should be reversed using SWAP gates</span></span>



## <a name="output--unit"></a><span data-ttu-id="28ddf-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28ddf-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

