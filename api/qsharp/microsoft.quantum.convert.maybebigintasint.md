---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: 1f10ac027f8f289e5ea554a7804abeb33def4df8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832770"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="a78e4-102">MaybeBigIntAsInt 函式</span><span class="sxs-lookup"><span data-stu-id="a78e4-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="a78e4-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="a78e4-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="a78e4-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a78e4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a78e4-105">盡可能將指定的大整數轉換為相等的整數。</span><span class="sxs-lookup"><span data-stu-id="a78e4-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="a78e4-106">函數會傳回一組產生的整數和一個布林值旗標，如果有可能的話，則為 true。</span><span class="sxs-lookup"><span data-stu-id="a78e4-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="a78e4-107">輸入</span><span class="sxs-lookup"><span data-stu-id="a78e4-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="a78e4-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a78e4-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="a78e4-109">Output： ([Int](xref:microsoft.quantum.lang-ref.int)，[Bool](xref:microsoft.quantum.lang-ref.bool)) </span><span class="sxs-lookup"><span data-stu-id="a78e4-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="a78e4-110">備註</span><span class="sxs-lookup"><span data-stu-id="a78e4-110">Remarks</span></span>

<span data-ttu-id="a78e4-111">如需詳細資訊，請參閱 [c # BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 函式。</span><span class="sxs-lookup"><span data-stu-id="a78e4-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>