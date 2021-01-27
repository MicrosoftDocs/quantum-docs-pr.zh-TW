---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: ApplyQuantumFourierTransform 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: d99000c21c79d2ca97b1fe92ad331c7ba8599700
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844766"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="cc33d-102">ApplyQuantumFourierTransform 操作</span><span class="sxs-lookup"><span data-stu-id="cc33d-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="cc33d-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cc33d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cc33d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc33d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc33d-105">在包含整數位節由小到大標記法的量子暫存器上執行量子傅立葉轉換。</span><span class="sxs-lookup"><span data-stu-id="cc33d-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cc33d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="cc33d-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="cc33d-107">qs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cc33d-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cc33d-108">套用量子傅立葉轉換的量子暫存器</span><span class="sxs-lookup"><span data-stu-id="cc33d-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="cc33d-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc33d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cc33d-110">備註</span><span class="sxs-lookup"><span data-stu-id="cc33d-110">Remarks</span></span>

<span data-ttu-id="cc33d-111">輸入和輸出假設是以位元組由小到大的編碼方式。</span><span class="sxs-lookup"><span data-stu-id="cc33d-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc33d-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cc33d-112">See Also</span></span>

- [<span data-ttu-id="cc33d-113">Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="cc33d-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)