---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: c28027f7a2533885102a54a028bec37eb608f2b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846712"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="0925e-102">ComputeReciprocalI 操作</span><span class="sxs-lookup"><span data-stu-id="0925e-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="0925e-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0925e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0925e-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="0925e-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="0925e-105">使用整數除法計算不帶正負號整數 x 的倒數 1/x。</span><span class="sxs-lookup"><span data-stu-id="0925e-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="0925e-106">結果（以整數來解讀）將會是 `floor(2^(2*n-1) / x)` 。</span><span class="sxs-lookup"><span data-stu-id="0925e-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0925e-107">輸入</span><span class="sxs-lookup"><span data-stu-id="0925e-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="0925e-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0925e-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0925e-109">n 位不帶正負號整數</span><span class="sxs-lookup"><span data-stu-id="0925e-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="0925e-110">結果： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0925e-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0925e-111">2n 位輸出的初始必須是 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="0925e-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0925e-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0925e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0925e-113">備註</span><span class="sxs-lookup"><span data-stu-id="0925e-113">Remarks</span></span>

<span data-ttu-id="0925e-114">針對輸入 x = 0，輸出將會是所有的輸出。</span><span class="sxs-lookup"><span data-stu-id="0925e-114">For the input x=0, the output will be all-ones.</span></span>