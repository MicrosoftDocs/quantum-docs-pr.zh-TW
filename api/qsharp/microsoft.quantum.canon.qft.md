---
uid: Microsoft.Quantum.Canon.QFT
title: QFT 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 8f1aa8c3680a068e500503ca25afa9a49e4ef5bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205521"
---
# <a name="qft-operation"></a><span data-ttu-id="78e5f-102">QFT 操作</span><span class="sxs-lookup"><span data-stu-id="78e5f-102">QFT operation</span></span>

<span data-ttu-id="78e5f-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="78e5f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="78e5f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78e5f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78e5f-105">在包含以大到小整數表示之整數的量子暫存器上執行量子傅立葉轉換。</span><span class="sxs-lookup"><span data-stu-id="78e5f-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="78e5f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="78e5f-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="78e5f-107">qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="78e5f-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="78e5f-108">套用量子傅立葉轉換的量子暫存器</span><span class="sxs-lookup"><span data-stu-id="78e5f-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="78e5f-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78e5f-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="78e5f-110">備註</span><span class="sxs-lookup"><span data-stu-id="78e5f-110">Remarks</span></span>

<span data-ttu-id="78e5f-111">輸入和輸出假設為位元組由大到小的編碼方式。</span><span class="sxs-lookup"><span data-stu-id="78e5f-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="78e5f-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="78e5f-112">See Also</span></span>

- [<span data-ttu-id="78e5f-113">Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="78e5f-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)