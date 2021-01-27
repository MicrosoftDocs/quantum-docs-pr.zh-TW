---
uid: Microsoft.Quantum.Canon.QFT
title: QFT 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 30f475c3850c248b5af58db1e4aac3638c4c0471
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852301"
---
# <a name="qft-operation"></a><span data-ttu-id="68176-102">QFT 操作</span><span class="sxs-lookup"><span data-stu-id="68176-102">QFT operation</span></span>

<span data-ttu-id="68176-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="68176-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="68176-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68176-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68176-105">在包含以大到小整數表示之整數的量子暫存器上執行量子傅立葉轉換。</span><span class="sxs-lookup"><span data-stu-id="68176-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="68176-106">輸入</span><span class="sxs-lookup"><span data-stu-id="68176-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="68176-107">qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="68176-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="68176-108">套用量子傅立葉轉換的量子暫存器</span><span class="sxs-lookup"><span data-stu-id="68176-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="68176-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="68176-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="68176-110">備註</span><span class="sxs-lookup"><span data-stu-id="68176-110">Remarks</span></span>

<span data-ttu-id="68176-111">輸入和輸出假設為位元組由大到小的編碼方式。</span><span class="sxs-lookup"><span data-stu-id="68176-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="68176-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="68176-112">See Also</span></span>

- [<span data-ttu-id="68176-113">Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="68176-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)