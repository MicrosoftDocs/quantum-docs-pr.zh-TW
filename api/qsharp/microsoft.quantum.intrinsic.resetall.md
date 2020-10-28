---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 00b7c0f508d76fb0f5b46c7ec00c0718469365a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697706"
---
# <a name="resetall-operation"></a><span data-ttu-id="d2672-102">ResetAll 操作</span><span class="sxs-lookup"><span data-stu-id="d2672-102">ResetAll operation</span></span>

<span data-ttu-id="d2672-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d2672-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d2672-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d2672-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d2672-105">假設有量子位陣列，請加以測量，並確保它們處於 | 0 ⟩狀態，讓它們可以安全地發行。</span><span class="sxs-lookup"><span data-stu-id="d2672-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d2672-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d2672-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="d2672-107">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d2672-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d2672-108">量子位的陣列，其狀態會重設為 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="d2672-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d2672-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d2672-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

