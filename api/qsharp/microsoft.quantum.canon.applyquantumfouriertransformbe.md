---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: a1f4a0a5e94465fc8bf3af344e2e19ee0d1d15e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841572"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="f33ef-102">ApplyQuantumFourierTransformBE 操作</span><span class="sxs-lookup"><span data-stu-id="f33ef-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="f33ef-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f33ef-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f33ef-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f33ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f33ef-105">在包含以大到小整數表示之整數的量子暫存器上執行量子傅立葉轉換。</span><span class="sxs-lookup"><span data-stu-id="f33ef-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f33ef-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f33ef-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="f33ef-107">qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="f33ef-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="f33ef-108">套用量子傅立葉轉換的量子暫存器</span><span class="sxs-lookup"><span data-stu-id="f33ef-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="f33ef-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f33ef-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f33ef-110">備註</span><span class="sxs-lookup"><span data-stu-id="f33ef-110">Remarks</span></span>

<span data-ttu-id="f33ef-111">輸入和輸出假設為位元組由大到小的編碼方式。</span><span class="sxs-lookup"><span data-stu-id="f33ef-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="f33ef-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f33ef-112">See Also</span></span>

- [<span data-ttu-id="f33ef-113">Canon. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="f33ef-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="f33ef-114">Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="f33ef-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)