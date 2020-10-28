---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701031"
---
# <a name="modulusl-function"></a><span data-ttu-id="b57cf-102">ModulusL 函式</span><span class="sxs-lookup"><span data-stu-id="b57cf-102">ModulusL function</span></span>

<span data-ttu-id="b57cf-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b57cf-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b57cf-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b57cf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b57cf-105">計算模數的標準 residue `value` `modulus` 。</span><span class="sxs-lookup"><span data-stu-id="b57cf-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="b57cf-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b57cf-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="b57cf-107">值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b57cf-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b57cf-108">計算 residue 的值</span><span class="sxs-lookup"><span data-stu-id="b57cf-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="b57cf-109">模數： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b57cf-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b57cf-110">Residues 所採用的模數必須是正數</span><span class="sxs-lookup"><span data-stu-id="b57cf-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="b57cf-111">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b57cf-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b57cf-112">0之間的整數 $r $，因此 `modulus - 1` `value - r` 模數可以整除</span><span class="sxs-lookup"><span data-stu-id="b57cf-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="b57cf-113">備註</span><span class="sxs-lookup"><span data-stu-id="b57cf-113">Remarks</span></span>

<span data-ttu-id="b57cf-114">此函式的行為與運算子 `%` 在 c # 和 Q # 中的運作方式不同，因為結果中的結果一律是0和之間的正整數 `modulus - 1` ，即使值為負數。</span><span class="sxs-lookup"><span data-stu-id="b57cf-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>