---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: f28f74d34fb4688739646da3dc12ae6734eb4ad4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698914"
---
# <a name="qftle-operation"></a><span data-ttu-id="7de81-102">QFTLE 操作</span><span class="sxs-lookup"><span data-stu-id="7de81-102">QFTLE operation</span></span>

<span data-ttu-id="7de81-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7de81-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7de81-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7de81-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7de81-105">在包含整數位節由小到大標記法的量子暫存器上執行量子傅立葉轉換。</span><span class="sxs-lookup"><span data-stu-id="7de81-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="7de81-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7de81-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="7de81-107">qs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7de81-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7de81-108">套用量子傅立葉轉換的量子暫存器</span><span class="sxs-lookup"><span data-stu-id="7de81-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="7de81-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7de81-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7de81-110">備註</span><span class="sxs-lookup"><span data-stu-id="7de81-110">Remarks</span></span>

<span data-ttu-id="7de81-111">輸入和輸出假設是以位元組由小到大的編碼方式。</span><span class="sxs-lookup"><span data-stu-id="7de81-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="7de81-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7de81-112">See Also</span></span>

- [<span data-ttu-id="7de81-113">Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="7de81-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)