---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220292"
---
# <a name="sequencei-function"></a><span data-ttu-id="43bf4-102">SequenceI 函式</span><span class="sxs-lookup"><span data-stu-id="43bf4-102">SequenceI function</span></span>

<span data-ttu-id="43bf4-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="43bf4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="43bf4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="43bf4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="43bf4-105">取得指定間隔內的整數陣列。</span><span class="sxs-lookup"><span data-stu-id="43bf4-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="43bf4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="43bf4-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="43bf4-107">來源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="43bf4-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="43bf4-108">間隔的內含開始索引。</span><span class="sxs-lookup"><span data-stu-id="43bf4-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="43bf4-109">至： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="43bf4-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="43bf4-110">不小於的間隔的內含結尾索引 `from` 。</span><span class="sxs-lookup"><span data-stu-id="43bf4-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="43bf4-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="43bf4-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="43bf4-112">陣列，其中包含數位的序列 `from` （ `from + 1` ，...） `to` 。</span><span class="sxs-lookup"><span data-stu-id="43bf4-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>