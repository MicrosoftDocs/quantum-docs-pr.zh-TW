---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220258"
---
# <a name="sequencel-function"></a><span data-ttu-id="b1e6e-102">SequenceL 函式</span><span class="sxs-lookup"><span data-stu-id="b1e6e-102">SequenceL function</span></span>

<span data-ttu-id="b1e6e-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b1e6e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b1e6e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1e6e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1e6e-105">取得指定間隔內的整數陣列。</span><span class="sxs-lookup"><span data-stu-id="b1e6e-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="b1e6e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b1e6e-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="b1e6e-107">from： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b1e6e-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b1e6e-108">間隔的內含開始索引。</span><span class="sxs-lookup"><span data-stu-id="b1e6e-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="b1e6e-109">至： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b1e6e-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b1e6e-110">不小於的間隔的內含結尾索引 `from` 。</span><span class="sxs-lookup"><span data-stu-id="b1e6e-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="b1e6e-111">Output： [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="b1e6e-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="b1e6e-112">陣列，其中包含數位的序列 `from` （ `from + 1` ，...） `to` 。</span><span class="sxs-lookup"><span data-stu-id="b1e6e-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1e6e-113">備註</span><span class="sxs-lookup"><span data-stu-id="b1e6e-113">Remarks</span></span>

<span data-ttu-id="b1e6e-114">和之間的 `from` 差異 `to` 必須符合 `Int` 值。</span><span class="sxs-lookup"><span data-stu-id="b1e6e-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>