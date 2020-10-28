---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: EncodeOp 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: da947cdc25cb0edd3a4144022bbfc6ecb84c647f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697974"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="e41c7-102">EncodeOp 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="e41c7-102">EncodeOp user defined type</span></span>

<span data-ttu-id="e41c7-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e41c7-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e41c7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e41c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e41c7-105">表示使用提供的臨時量子位將實體暫存器編碼為邏輯暫存器的作業。</span><span class="sxs-lookup"><span data-stu-id="e41c7-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="e41c7-106">第一個引數會被視為將會編碼的實體暫存器，而第二個引數則會被視為將使用的臨時暫存器。</span><span class="sxs-lookup"><span data-stu-id="e41c7-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

