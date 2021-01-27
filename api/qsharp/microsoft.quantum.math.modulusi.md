---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847295"
---
# <a name="modulusi-function"></a><span data-ttu-id="f2708-102">ModulusI 函式</span><span class="sxs-lookup"><span data-stu-id="f2708-102">ModulusI function</span></span>

<span data-ttu-id="f2708-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f2708-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f2708-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2708-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2708-105">計算模數的標準 residue `value` `modulus` 。</span><span class="sxs-lookup"><span data-stu-id="f2708-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="f2708-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f2708-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="f2708-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2708-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2708-108">計算 residue 的值</span><span class="sxs-lookup"><span data-stu-id="f2708-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="f2708-109">模數： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2708-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2708-110">Residues 所採用的模數必須是正數</span><span class="sxs-lookup"><span data-stu-id="f2708-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="f2708-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2708-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2708-112">0之間的整數 $r $，因此 `modulus - 1` `value - r` 模數可以整除</span><span class="sxs-lookup"><span data-stu-id="f2708-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="f2708-113">備註</span><span class="sxs-lookup"><span data-stu-id="f2708-113">Remarks</span></span>

<span data-ttu-id="f2708-114">此函式的行為與運算子 `%` 在 c # 和 Q # 中的運作方式不同，因為結果中的結果一律是0和之間的非負整數 `modulus - 1` ，即使值為負數。</span><span class="sxs-lookup"><span data-stu-id="f2708-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>