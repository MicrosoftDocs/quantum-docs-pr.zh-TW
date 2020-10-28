---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697599"
---
# <a name="multim-operation"></a><span data-ttu-id="9fcf1-102">MultiM 操作</span><span class="sxs-lookup"><span data-stu-id="9fcf1-102">MultiM operation</span></span>

<span data-ttu-id="9fcf1-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="9fcf1-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="9fcf1-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9fcf1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9fcf1-105">以標準為單位測量指定陣列中的每個量子位。</span><span class="sxs-lookup"><span data-stu-id="9fcf1-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="9fcf1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9fcf1-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="9fcf1-107">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9fcf1-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9fcf1-108">要測量的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="9fcf1-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="9fcf1-109">輸出： __無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="9fcf1-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="9fcf1-110">測量結果的陣列。</span><span class="sxs-lookup"><span data-stu-id="9fcf1-110">An array of measurement results.</span></span>