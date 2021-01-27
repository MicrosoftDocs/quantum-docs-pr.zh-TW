---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: cb4cf68753468952c7541fae23250ed1fd1914f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843373"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="17cb1-102">BigEndianAsLittleEndian 函式</span><span class="sxs-lookup"><span data-stu-id="17cb1-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="17cb1-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="17cb1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="17cb1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17cb1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="17cb1-105">藉 `BigEndian` `LittleEndian` 由反轉量子位順序，將量子位暫存器轉換成量子位暫存器。</span><span class="sxs-lookup"><span data-stu-id="17cb1-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="17cb1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="17cb1-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="17cb1-107">輸入： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="17cb1-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="17cb1-108">量子位 register `BigEndian` 格式。</span><span class="sxs-lookup"><span data-stu-id="17cb1-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="17cb1-109">輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="17cb1-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="17cb1-110">量子位 register `LittleEndian` 格式。</span><span class="sxs-lookup"><span data-stu-id="17cb1-110">Qubit register in `LittleEndian` format.</span></span>