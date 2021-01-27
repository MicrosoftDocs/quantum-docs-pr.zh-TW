---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: c89288e1eb421fd5abd8fcd5d9c12049aa47ac89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843081"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="ce7ec-102">LittleEndianAsBigEndian 函式</span><span class="sxs-lookup"><span data-stu-id="ce7ec-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="ce7ec-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ce7ec-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ce7ec-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ce7ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ce7ec-105">藉 `LittleEndian` `BigEndian` 由反轉量子位順序，將量子位暫存器轉換成量子位暫存器。</span><span class="sxs-lookup"><span data-stu-id="ce7ec-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="ce7ec-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ce7ec-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="ce7ec-107">輸入： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ce7ec-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ce7ec-108">量子位 register `LittleEndian` 格式。</span><span class="sxs-lookup"><span data-stu-id="ce7ec-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="ce7ec-109">輸出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="ce7ec-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="ce7ec-110">量子位 register `BigEndian` 格式。</span><span class="sxs-lookup"><span data-stu-id="ce7ec-110">Qubit register in `BigEndian` format.</span></span>