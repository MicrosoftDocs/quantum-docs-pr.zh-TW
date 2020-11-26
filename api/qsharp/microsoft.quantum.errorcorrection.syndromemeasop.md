---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200249"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="dc170-102">SyndromeMeasOp 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="dc170-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="dc170-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="dc170-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="dc170-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc170-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc170-105">表示用來測量錯誤修正程式碼區塊之症狀的作業。</span><span class="sxs-lookup"><span data-stu-id="dc170-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="dc170-106">備註</span><span class="sxs-lookup"><span data-stu-id="dc170-106">Remarks</span></span>

<span data-ttu-id="dc170-107">簽章 `(LogicalRegister => Syndrome)` 代表一項作業，該作業會共同在的量子位上運作 `LogicalRegister` ，而有些輔助量子位則接著輔助量子位的度量，以將 `Syndrome` 代表 `Result[]` 這些測量之的值解壓縮。</span><span class="sxs-lookup"><span data-stu-id="dc170-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc170-108">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dc170-108">See Also</span></span>

- [<span data-ttu-id="dc170-109">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="dc170-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="dc170-110">ErrorCorrection 的症狀</span><span class="sxs-lookup"><span data-stu-id="dc170-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)