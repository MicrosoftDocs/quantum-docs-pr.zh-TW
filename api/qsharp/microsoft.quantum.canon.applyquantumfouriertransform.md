---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: ApplyQuantumFourierTransform 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: fa8d135c0665f0a576229797d208b321ba0329a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699252"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="39243-102">ApplyQuantumFourierTransform 操作</span><span class="sxs-lookup"><span data-stu-id="39243-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="39243-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39243-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39243-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39243-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39243-105">在包含整數位節由小到大標記法的量子暫存器上執行量子傅立葉轉換。</span><span class="sxs-lookup"><span data-stu-id="39243-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="39243-106">輸入</span><span class="sxs-lookup"><span data-stu-id="39243-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="39243-107">qs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="39243-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="39243-108">套用量子傅立葉轉換的量子暫存器</span><span class="sxs-lookup"><span data-stu-id="39243-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="39243-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39243-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="39243-110">備註</span><span class="sxs-lookup"><span data-stu-id="39243-110">Remarks</span></span>

<span data-ttu-id="39243-111">輸入和輸出假設是以位元組由小到大的編碼方式。</span><span class="sxs-lookup"><span data-stu-id="39243-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="39243-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="39243-112">See Also</span></span>

- [<span data-ttu-id="39243-113">Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="39243-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)