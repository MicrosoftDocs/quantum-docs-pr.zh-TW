---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850977"
---
# <a name="sequencel-function"></a><span data-ttu-id="64053-102">SequenceL 函式</span><span class="sxs-lookup"><span data-stu-id="64053-102">SequenceL function</span></span>

<span data-ttu-id="64053-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="64053-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="64053-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64053-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64053-105">取得指定間隔內的整數陣列。</span><span class="sxs-lookup"><span data-stu-id="64053-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="64053-106">輸入</span><span class="sxs-lookup"><span data-stu-id="64053-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="64053-107">from： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="64053-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="64053-108">間隔的內含開始索引。</span><span class="sxs-lookup"><span data-stu-id="64053-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="64053-109">至： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="64053-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="64053-110">不小於的間隔的內含結尾索引 `from` 。</span><span class="sxs-lookup"><span data-stu-id="64053-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="64053-111">Output： [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="64053-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="64053-112">陣列，其中包含數位的序列 `from` （ `from + 1` ，...） `to` 。</span><span class="sxs-lookup"><span data-stu-id="64053-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="example"></a><span data-ttu-id="64053-113">範例</span><span class="sxs-lookup"><span data-stu-id="64053-113">Example</span></span>

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a><span data-ttu-id="64053-114">備註</span><span class="sxs-lookup"><span data-stu-id="64053-114">Remarks</span></span>

<span data-ttu-id="64053-115">和之間的 `from` 差異 `to` 必須符合 `Int` 值。</span><span class="sxs-lookup"><span data-stu-id="64053-115">The difference between `from` and `to` must fit into an `Int` value.</span></span>