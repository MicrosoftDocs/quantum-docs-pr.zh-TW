---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: DecodeOp 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: f1fc2851b7ed8b12cf8a47fabe794235a3083d31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200997"
---
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="5a5cf-102">DecodeOp 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="5a5cf-102">DecodeOp user defined type</span></span>

<span data-ttu-id="5a5cf-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="5a5cf-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="5a5cf-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a5cf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a5cf-105">代表將編碼的暫存器解碼成實體暫存器的作業，以及用來記錄症狀的臨時量子位。</span><span class="sxs-lookup"><span data-stu-id="5a5cf-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="5a5cf-106">DecodeOp 的引數與從 EncodeOp 傳回的相同，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="5a5cf-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

