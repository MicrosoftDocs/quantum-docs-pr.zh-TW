---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 75656ba188a1b822eb42e98412365bf5873bf46e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698335"
---
# <a name="boolarrayasbigint-function"></a><span data-ttu-id="56f98-102">BoolArrayAsBigInt 函式</span><span class="sxs-lookup"><span data-stu-id="56f98-102">BoolArrayAsBigInt function</span></span>

<span data-ttu-id="56f98-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="56f98-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="56f98-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="56f98-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="56f98-105">將指定的布林值陣列轉換為相等的大整數。</span><span class="sxs-lookup"><span data-stu-id="56f98-105">Converts a given array of Booleans to an equivalent big integer.</span></span>
<span data-ttu-id="56f98-106">陣列的0元素是大整數中最不重要的位。</span><span class="sxs-lookup"><span data-stu-id="56f98-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a><span data-ttu-id="56f98-107">輸入</span><span class="sxs-lookup"><span data-stu-id="56f98-107">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="56f98-108">a： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="56f98-108">a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>





## <a name="output--bigint"></a><span data-ttu-id="56f98-109">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="56f98-109">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="56f98-110">備註</span><span class="sxs-lookup"><span data-stu-id="56f98-110">Remarks</span></span>

<span data-ttu-id="56f98-111">如需詳細資訊，請參閱 [c # BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 函式。</span><span class="sxs-lookup"><span data-stu-id="56f98-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>