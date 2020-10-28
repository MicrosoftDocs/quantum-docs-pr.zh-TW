---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699902"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="a3593-102">ComputeReciprocalI 操作</span><span class="sxs-lookup"><span data-stu-id="a3593-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="a3593-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a3593-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a3593-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3593-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3593-105">使用整數除法計算不帶正負號整數 x 的倒數 1/x。</span><span class="sxs-lookup"><span data-stu-id="a3593-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="a3593-106">結果（以整數來解讀）將會是 `floor(2^(2*n-1) / x)` 。</span><span class="sxs-lookup"><span data-stu-id="a3593-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="a3593-107">輸入</span><span class="sxs-lookup"><span data-stu-id="a3593-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="a3593-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a3593-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a3593-109">n 位不帶正負號整數</span><span class="sxs-lookup"><span data-stu-id="a3593-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="a3593-110">結果： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a3593-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a3593-111">2n 位輸出的初始必須是 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="a3593-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a3593-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3593-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a3593-113">備註</span><span class="sxs-lookup"><span data-stu-id="a3593-113">Remarks</span></span>

<span data-ttu-id="a3593-114">針對輸入 x = 0，輸出將會是所有的輸出。</span><span class="sxs-lookup"><span data-stu-id="a3593-114">For the input x=0, the output will be all-ones.</span></span>