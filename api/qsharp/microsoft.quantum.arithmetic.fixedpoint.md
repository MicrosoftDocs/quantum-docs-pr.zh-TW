---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: f1370cd2f8a7d6488ae0f6be841abd95e61f038e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699875"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="f2204-102">FixedPoint 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="f2204-102">FixedPoint user defined type</span></span>

<span data-ttu-id="f2204-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f2204-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f2204-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f2204-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f2204-105">代表量子位編碼固定點數位的暫存器。</span><span class="sxs-lookup"><span data-stu-id="f2204-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="f2204-106">包含的整數等於二進位點左邊的量子位數目，也就是權數大於或等於1的量子位，以及量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="f2204-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

