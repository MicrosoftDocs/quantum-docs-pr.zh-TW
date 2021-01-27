---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 18e85120647c5a1f41ccab5fbfb27ea602a279af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843194"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="ce3b4-102">FixedPoint 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="ce3b4-102">FixedPoint user defined type</span></span>

<span data-ttu-id="ce3b4-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ce3b4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ce3b4-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="ce3b4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="ce3b4-105">代表量子位編碼固定點數位的暫存器。</span><span class="sxs-lookup"><span data-stu-id="ce3b4-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="ce3b4-106">包含的整數等於二進位點左邊的量子位數目，也就是權數大於或等於1的量子位，以及量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="ce3b4-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

