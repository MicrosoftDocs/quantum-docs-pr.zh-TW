---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 65074b74bcc952efc8b2a9473b2a010bdda42990
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699938"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="4fa7e-102">BigEndianAsLittleEndian 函式</span><span class="sxs-lookup"><span data-stu-id="4fa7e-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="4fa7e-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4fa7e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4fa7e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4fa7e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4fa7e-105">藉 `BigEndian` `LittleEndian` 由反轉量子位順序，將量子位暫存器轉換成量子位暫存器。</span><span class="sxs-lookup"><span data-stu-id="4fa7e-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="4fa7e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="4fa7e-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="4fa7e-107">輸入： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="4fa7e-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="4fa7e-108">量子位 register `BigEndian` 格式。</span><span class="sxs-lookup"><span data-stu-id="4fa7e-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="4fa7e-109">輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4fa7e-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4fa7e-110">量子位 register `LittleEndian` 格式。</span><span class="sxs-lookup"><span data-stu-id="4fa7e-110">Qubit register in `LittleEndian` format.</span></span>