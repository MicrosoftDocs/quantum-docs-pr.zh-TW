---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 30fd172584b36601c4b81deff494cf55964518f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205434"
---
# <a name="repeatc-operation"></a><span data-ttu-id="908ab-102">RepeatC 操作</span><span class="sxs-lookup"><span data-stu-id="908ab-102">RepeatC operation</span></span>

<span data-ttu-id="908ab-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="908ab-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="908ab-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="908ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="908ab-105">以指定的次數重複作業。</span><span class="sxs-lookup"><span data-stu-id="908ab-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="908ab-106">輸入</span><span class="sxs-lookup"><span data-stu-id="908ab-106">Input</span></span>

### <a name="op--tinput--unit--is-ctl"></a><span data-ttu-id="908ab-107">op： ' TInput => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="908ab-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="908ab-108">要重複呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="908ab-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="908ab-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="908ab-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="908ab-110">要呼叫的次數 `op` 。</span><span class="sxs-lookup"><span data-stu-id="908ab-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="908ab-111">輸入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="908ab-111">input : 'TInput</span></span>

<span data-ttu-id="908ab-112">要傳遞至的輸入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="908ab-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="908ab-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="908ab-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="908ab-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="908ab-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="908ab-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="908ab-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="908ab-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="908ab-116">See Also</span></span>

- [<span data-ttu-id="908ab-117">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="908ab-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="908ab-118">Canon. 重複</span><span class="sxs-lookup"><span data-stu-id="908ab-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="908ab-119">Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="908ab-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="908ab-120">Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="908ab-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)