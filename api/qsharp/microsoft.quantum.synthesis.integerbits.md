---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855410"
---
# <a name="integerbits-function"></a><span data-ttu-id="06111-102">IntegerBits 函式</span><span class="sxs-lookup"><span data-stu-id="06111-102">IntegerBits function</span></span>

<span data-ttu-id="06111-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="06111-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="06111-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06111-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06111-105">傳回設定整數位的所有位置。</span><span class="sxs-lookup"><span data-stu-id="06111-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="06111-106">輸入</span><span class="sxs-lookup"><span data-stu-id="06111-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="06111-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="06111-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="06111-108">非負數值。</span><span class="sxs-lookup"><span data-stu-id="06111-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="06111-109">長度： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="06111-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="06111-110">的二進位擴充中的位數目 `value` 。</span><span class="sxs-lookup"><span data-stu-id="06111-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="06111-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="06111-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="06111-112">包含所有位位置的陣列 (從0開始，在二元擴充中，會將 `value` 所有位視為最高的位置 1) `length - 1` 。</span><span class="sxs-lookup"><span data-stu-id="06111-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="06111-113">所有位置都會依位置以遞增順序排列在陣列中。</span><span class="sxs-lookup"><span data-stu-id="06111-113">All positions are ordered in the array by position in an increasing order.</span></span>

## <a name="example"></a><span data-ttu-id="06111-114">範例</span><span class="sxs-lookup"><span data-stu-id="06111-114">Example</span></span>

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```