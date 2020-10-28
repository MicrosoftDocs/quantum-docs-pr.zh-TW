---
uid: Microsoft.Quantum.Math.DivRemL
title: DivRemL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: DivRemL
qsharp.summary: Divides one BigInteger value by another, returns the result and the remainder as a tuple.
ms.openlocfilehash: d2ca91e0c3e8d69902234689359da7b73a8f7d1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700643"
---
# <a name="divreml-function"></a><span data-ttu-id="5d042-102">DivRemL 函式</span><span class="sxs-lookup"><span data-stu-id="5d042-102">DivRemL function</span></span>

<span data-ttu-id="5d042-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5d042-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5d042-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d042-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d042-105">將一個 BigInteger 值除以另一個值，並以元組傳回結果和餘數。</span><span class="sxs-lookup"><span data-stu-id="5d042-105">Divides one BigInteger value by another, returns the result and the remainder as a tuple.</span></span>

```qsharp
function DivRemL (dividend : BigInt, divisor : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="5d042-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5d042-106">Input</span></span>

### <a name="dividend--bigint"></a><span data-ttu-id="5d042-107">被除數： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5d042-107">dividend : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="divisor--bigint"></a><span data-ttu-id="5d042-108">除數： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5d042-108">divisor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigintbigint"></a><span data-ttu-id="5d042-109">輸出： ([Bigint](xref:microsoft.quantum.lang-ref.bigint)、[Bigint](xref:microsoft.quantum.lang-ref.bigint)) </span><span class="sxs-lookup"><span data-stu-id="5d042-109">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>



## <a name="remarks"></a><span data-ttu-id="5d042-110">備註</span><span class="sxs-lookup"><span data-stu-id="5d042-110">Remarks</span></span>

<span data-ttu-id="5d042-111">如需詳細資訊，請參閱 [BigInteger. DivRem](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem) 。</span><span class="sxs-lookup"><span data-stu-id="5d042-111">See [System.Numerics.BigInteger.DivRem](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem) for more details.</span></span>