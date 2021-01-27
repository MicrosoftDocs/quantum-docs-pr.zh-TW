---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: b7f4083bde84c204611ea33746ae351a3e27b946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857001"
---
# <a name="multim-operation"></a><span data-ttu-id="b2be2-102">MultiM 操作</span><span class="sxs-lookup"><span data-stu-id="b2be2-102">MultiM operation</span></span>

<span data-ttu-id="b2be2-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="b2be2-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="b2be2-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2be2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2be2-105">以標準為單位測量指定陣列中的每個量子位。</span><span class="sxs-lookup"><span data-stu-id="b2be2-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="b2be2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b2be2-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="b2be2-107">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b2be2-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b2be2-108">要測量的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="b2be2-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="b2be2-109">輸出：__無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="b2be2-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="b2be2-110">測量結果的陣列。</span><span class="sxs-lookup"><span data-stu-id="b2be2-110">An array of measurement results.</span></span>