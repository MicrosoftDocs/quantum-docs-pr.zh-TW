---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: DecodeOp 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: 0733ec016e50a320b162b111c7d87c32140fdacb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697991"
---
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="3ea2d-102">DecodeOp 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="3ea2d-102">DecodeOp user defined type</span></span>

<span data-ttu-id="3ea2d-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="3ea2d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="3ea2d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ea2d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ea2d-105">代表將編碼的暫存器解碼成實體暫存器的作業，以及用來記錄症狀的臨時量子位。</span><span class="sxs-lookup"><span data-stu-id="3ea2d-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="3ea2d-106">DecodeOp 的引數與從 EncodeOp 傳回的相同，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="3ea2d-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

