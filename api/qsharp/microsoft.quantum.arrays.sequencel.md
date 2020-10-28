---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699423"
---
# <a name="sequencel-function"></a><span data-ttu-id="01cc6-102">SequenceL 函式</span><span class="sxs-lookup"><span data-stu-id="01cc6-102">SequenceL function</span></span>

<span data-ttu-id="01cc6-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="01cc6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="01cc6-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01cc6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01cc6-105">取得指定間隔內的整數陣列。</span><span class="sxs-lookup"><span data-stu-id="01cc6-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="01cc6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="01cc6-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="01cc6-107">from： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="01cc6-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="01cc6-108">間隔的內含開始索引。</span><span class="sxs-lookup"><span data-stu-id="01cc6-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="01cc6-109">至： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="01cc6-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="01cc6-110">不小於的間隔的內含結尾索引 `from` 。</span><span class="sxs-lookup"><span data-stu-id="01cc6-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="01cc6-111">Output： [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="01cc6-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="01cc6-112">陣列，其中包含數位的序列 `from` （ `from + 1` ，...） `to` 。</span><span class="sxs-lookup"><span data-stu-id="01cc6-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="01cc6-113">備註</span><span class="sxs-lookup"><span data-stu-id="01cc6-113">Remarks</span></span>

<span data-ttu-id="01cc6-114">和之間的 `from` 差異 `to` 必須符合 `Int` 值。</span><span class="sxs-lookup"><span data-stu-id="01cc6-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>