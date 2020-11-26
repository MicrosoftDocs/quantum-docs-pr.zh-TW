---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226990"
---
# <a name="multim-operation"></a><span data-ttu-id="ec2e1-102">MultiM 操作</span><span class="sxs-lookup"><span data-stu-id="ec2e1-102">MultiM operation</span></span>

<span data-ttu-id="ec2e1-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="ec2e1-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="ec2e1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec2e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec2e1-105">以標準為單位測量指定陣列中的每個量子位。</span><span class="sxs-lookup"><span data-stu-id="ec2e1-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="ec2e1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ec2e1-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="ec2e1-107">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ec2e1-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ec2e1-108">要測量的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="ec2e1-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ec2e1-109">輸出：__無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="ec2e1-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="ec2e1-110">測量結果的陣列。</span><span class="sxs-lookup"><span data-stu-id="ec2e1-110">An array of measurement results.</span></span>