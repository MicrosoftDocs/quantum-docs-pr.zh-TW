---
uid: Microsoft.Quantum.Math.DivRemL
title: DivRemL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: DivRemL
qsharp.summary: Divides one BigInteger value by another, returns the result and the remainder as a tuple.
ms.openlocfilehash: 40ce295b82d138ad0b5261641c7f3649631d309d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210840"
---
# <a name="divreml-function"></a><span data-ttu-id="a1a7a-102">DivRemL 函式</span><span class="sxs-lookup"><span data-stu-id="a1a7a-102">DivRemL function</span></span>

<span data-ttu-id="a1a7a-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a1a7a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a1a7a-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a1a7a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a1a7a-105">將一個 BigInteger 值除以另一個值，並以元組傳回結果和餘數。</span><span class="sxs-lookup"><span data-stu-id="a1a7a-105">Divides one BigInteger value by another, returns the result and the remainder as a tuple.</span></span>

```qsharp
function DivRemL (dividend : BigInt, divisor : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="a1a7a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a1a7a-106">Input</span></span>

### <a name="dividend--bigint"></a><span data-ttu-id="a1a7a-107">被除數： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a1a7a-107">dividend : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="divisor--bigint"></a><span data-ttu-id="a1a7a-108">除數： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a1a7a-108">divisor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigintbigint"></a><span data-ttu-id="a1a7a-109">輸出： ([Bigint](xref:microsoft.quantum.lang-ref.bigint)、[Bigint](xref:microsoft.quantum.lang-ref.bigint)) </span><span class="sxs-lookup"><span data-stu-id="a1a7a-109">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>



## <a name="remarks"></a><span data-ttu-id="a1a7a-110">備註</span><span class="sxs-lookup"><span data-stu-id="a1a7a-110">Remarks</span></span>

<span data-ttu-id="a1a7a-111">如需詳細資訊，請參閱 [BigInteger. DivRem](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem) 。</span><span class="sxs-lookup"><span data-stu-id="a1a7a-111">See [System.Numerics.BigInteger.DivRem](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem) for more details.</span></span>