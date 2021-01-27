---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 9ae3123a64b2a886df3b7575b2840522f9b011ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852231"
---
# <a name="repeata-operation"></a><span data-ttu-id="95942-102">RepeatA 操作</span><span class="sxs-lookup"><span data-stu-id="95942-102">RepeatA operation</span></span>

<span data-ttu-id="95942-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="95942-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="95942-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95942-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95942-105">以指定的次數重複作業。</span><span class="sxs-lookup"><span data-stu-id="95942-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="95942-106">輸入</span><span class="sxs-lookup"><span data-stu-id="95942-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="95942-107">op： ' TInput => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="95942-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="95942-108">要重複呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="95942-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="95942-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95942-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95942-110">要呼叫的次數 `op` 。</span><span class="sxs-lookup"><span data-stu-id="95942-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="95942-111">輸入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="95942-111">input : 'TInput</span></span>

<span data-ttu-id="95942-112">要傳遞至的輸入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="95942-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="95942-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95942-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="95942-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="95942-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="95942-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="95942-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="95942-116">範例</span><span class="sxs-lookup"><span data-stu-id="95942-116">Example</span></span>

<span data-ttu-id="95942-117">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="95942-117">The following are equivalent:</span></span>

```qsharp
RepeatA(U, 17, target);
(BoundA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="95942-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="95942-118">See Also</span></span>

- [<span data-ttu-id="95942-119">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="95942-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="95942-120">Canon. 重複</span><span class="sxs-lookup"><span data-stu-id="95942-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="95942-121">Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="95942-121">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="95942-122">Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="95942-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)