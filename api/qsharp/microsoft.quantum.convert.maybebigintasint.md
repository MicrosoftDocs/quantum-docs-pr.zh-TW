---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: b91912f6f669afad888e71174fef6e2e6f8e7156
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698283"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="92c64-102">MaybeBigIntAsInt 函式</span><span class="sxs-lookup"><span data-stu-id="92c64-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="92c64-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="92c64-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="92c64-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92c64-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92c64-105">盡可能將指定的大整數轉換為相等的整數。</span><span class="sxs-lookup"><span data-stu-id="92c64-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="92c64-106">函數會傳回一組產生的整數和一個布林值旗標，如果有可能的話，則為 true。</span><span class="sxs-lookup"><span data-stu-id="92c64-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="92c64-107">輸入</span><span class="sxs-lookup"><span data-stu-id="92c64-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="92c64-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="92c64-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="92c64-109">Output： ([Int](xref:microsoft.quantum.lang-ref.int)，[Bool](xref:microsoft.quantum.lang-ref.bool)) </span><span class="sxs-lookup"><span data-stu-id="92c64-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="92c64-110">備註</span><span class="sxs-lookup"><span data-stu-id="92c64-110">Remarks</span></span>

<span data-ttu-id="92c64-111">如需詳細資訊，請參閱 [c # BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 函式。</span><span class="sxs-lookup"><span data-stu-id="92c64-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>