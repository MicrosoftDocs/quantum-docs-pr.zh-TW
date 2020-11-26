---
uid: Microsoft.Quantum.Simulation.Unitary
title: 單一使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: c34d84fb5f319c285356b284bd1f1c18ec64ef46
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192140"
---
# <a name="unitary-user-defined-type"></a><span data-ttu-id="88004-102">單一使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="88004-102">Unitary user defined type</span></span>

<span data-ttu-id="88004-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="88004-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="88004-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88004-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88004-105">表示單一運算子下的演進。</span><span class="sxs-lookup"><span data-stu-id="88004-105">Represents evolution under a unitary operator.</span></span>

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```

