---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699251"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="7de0f-102">ApplyQuantumFourierTransformBE 操作</span><span class="sxs-lookup"><span data-stu-id="7de0f-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="7de0f-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7de0f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7de0f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7de0f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7de0f-105">在包含以大到小整數表示之整數的量子暫存器上執行量子傅立葉轉換。</span><span class="sxs-lookup"><span data-stu-id="7de0f-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="7de0f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7de0f-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="7de0f-107">qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="7de0f-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="7de0f-108">套用量子傅立葉轉換的量子暫存器</span><span class="sxs-lookup"><span data-stu-id="7de0f-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="7de0f-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7de0f-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7de0f-110">備註</span><span class="sxs-lookup"><span data-stu-id="7de0f-110">Remarks</span></span>

<span data-ttu-id="7de0f-111">輸入和輸出假設為位元組由大到小的編碼方式。</span><span class="sxs-lookup"><span data-stu-id="7de0f-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="7de0f-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7de0f-112">See Also</span></span>

- [<span data-ttu-id="7de0f-113">Canon. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="7de0f-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="7de0f-114">Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="7de0f-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)