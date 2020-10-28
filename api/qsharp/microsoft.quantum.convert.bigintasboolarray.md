---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: BigIntAsBoolArray 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 13ba5b6dbf477dd1a02f24da5b7aca9bdb30ad2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698338"
---
# <a name="bigintasboolarray-function"></a><span data-ttu-id="88372-102">BigIntAsBoolArray 函式</span><span class="sxs-lookup"><span data-stu-id="88372-102">BigIntAsBoolArray function</span></span>

<span data-ttu-id="88372-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="88372-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="88372-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="88372-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="88372-105">將指定的大整數轉換為布林值陣列。</span><span class="sxs-lookup"><span data-stu-id="88372-105">Converts a given big integer to an array of Booleans.</span></span>
<span data-ttu-id="88372-106">陣列的0元素是大整數中最不重要的位。</span><span class="sxs-lookup"><span data-stu-id="88372-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a><span data-ttu-id="88372-107">輸入</span><span class="sxs-lookup"><span data-stu-id="88372-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="88372-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="88372-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bool"></a><span data-ttu-id="88372-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="88372-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="88372-110">備註</span><span class="sxs-lookup"><span data-stu-id="88372-110">Remarks</span></span>

<span data-ttu-id="88372-111">如需詳細資訊，請參閱 [c # BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 函式。</span><span class="sxs-lookup"><span data-stu-id="88372-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>