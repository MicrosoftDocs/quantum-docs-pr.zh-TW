---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 8c2e6150a839bb0cd4c311c821b78a080288cd22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699834"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="8890f-102">LittleEndianAsBigEndian 函式</span><span class="sxs-lookup"><span data-stu-id="8890f-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="8890f-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8890f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8890f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8890f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8890f-105">藉 `LittleEndian` `BigEndian` 由反轉量子位順序，將量子位暫存器轉換成量子位暫存器。</span><span class="sxs-lookup"><span data-stu-id="8890f-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="8890f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="8890f-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="8890f-107">輸入： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8890f-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8890f-108">量子位 register `LittleEndian` 格式。</span><span class="sxs-lookup"><span data-stu-id="8890f-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="8890f-109">輸出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="8890f-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="8890f-110">量子位 register `BigEndian` 格式。</span><span class="sxs-lookup"><span data-stu-id="8890f-110">Qubit register in `BigEndian` format.</span></span>