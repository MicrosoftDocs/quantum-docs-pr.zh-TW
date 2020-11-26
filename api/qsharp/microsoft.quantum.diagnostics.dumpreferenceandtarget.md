---
uid: Microsoft.Quantum.Diagnostics.DumpReferenceAndTarget
title: DumpReferenceAndTarget 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpReferenceAndTarget
qsharp.summary: Uses DumpRegister to provide diagnostics on the state of a reference and target register. Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.
ms.openlocfilehash: ef7e59b1561be04cba5839ebc397702b6c1df5bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202034"
---
# <a name="dumpreferenceandtarget-operation"></a><span data-ttu-id="7b372-102">DumpReferenceAndTarget 操作</span><span class="sxs-lookup"><span data-stu-id="7b372-102">DumpReferenceAndTarget operation</span></span>

<span data-ttu-id="7b372-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7b372-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7b372-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b372-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b372-105">使用 DumpRegister 來提供參考和目標暫存器狀態的診斷。</span><span class="sxs-lookup"><span data-stu-id="7b372-105">Uses DumpRegister to provide diagnostics on the state of a reference and target register.</span></span> <span data-ttu-id="7b372-106">撰寫為個別的作業，以允許將覆寫和解讀為個別的暫存器，而不是單一組合的暫存器。</span><span class="sxs-lookup"><span data-stu-id="7b372-106">Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.</span></span>

```qsharp
operation DumpReferenceAndTarget (reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7b372-107">輸入</span><span class="sxs-lookup"><span data-stu-id="7b372-107">Input</span></span>

### <a name="reference--qubit"></a><span data-ttu-id="7b372-108">參考： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7b372-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="7b372-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7b372-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="7b372-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b372-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

