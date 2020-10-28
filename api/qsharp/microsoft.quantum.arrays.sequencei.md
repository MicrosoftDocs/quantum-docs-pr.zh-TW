---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699426"
---
# <a name="sequencei-function"></a><span data-ttu-id="2a6a3-102">SequenceI 函式</span><span class="sxs-lookup"><span data-stu-id="2a6a3-102">SequenceI function</span></span>

<span data-ttu-id="2a6a3-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2a6a3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2a6a3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a6a3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a6a3-105">取得指定間隔內的整數陣列。</span><span class="sxs-lookup"><span data-stu-id="2a6a3-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="2a6a3-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2a6a3-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="2a6a3-107">來源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a6a3-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a6a3-108">間隔的內含開始索引。</span><span class="sxs-lookup"><span data-stu-id="2a6a3-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="2a6a3-109">至： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a6a3-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a6a3-110">不小於的間隔的內含結尾索引 `from` 。</span><span class="sxs-lookup"><span data-stu-id="2a6a3-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="2a6a3-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2a6a3-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2a6a3-112">陣列，其中包含數位的序列 `from` （ `from + 1` ，...） `to` 。</span><span class="sxs-lookup"><span data-stu-id="2a6a3-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>