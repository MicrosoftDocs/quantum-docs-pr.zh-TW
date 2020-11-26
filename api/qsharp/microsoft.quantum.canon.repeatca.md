---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 24606486b3d5703065a7c7f62d3bbc7e3d07615f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205400"
---
# <a name="repeatca-operation"></a><span data-ttu-id="ebcd4-102">RepeatCA 操作</span><span class="sxs-lookup"><span data-stu-id="ebcd4-102">RepeatCA operation</span></span>

<span data-ttu-id="ebcd4-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ebcd4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ebcd4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebcd4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebcd4-105">以指定的次數重複作業。</span><span class="sxs-lookup"><span data-stu-id="ebcd4-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ebcd4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ebcd4-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="ebcd4-107">op： ' TInput => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="ebcd4-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ebcd4-108">要重複呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="ebcd4-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="ebcd4-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ebcd4-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ebcd4-110">要呼叫的次數 `op` 。</span><span class="sxs-lookup"><span data-stu-id="ebcd4-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="ebcd4-111">輸入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="ebcd4-111">input : 'TInput</span></span>

<span data-ttu-id="ebcd4-112">要傳遞至的輸入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="ebcd4-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ebcd4-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ebcd4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ebcd4-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="ebcd4-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="ebcd4-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="ebcd4-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="ebcd4-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ebcd4-116">See Also</span></span>

- [<span data-ttu-id="ebcd4-117">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="ebcd4-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="ebcd4-118">Canon. 重複</span><span class="sxs-lookup"><span data-stu-id="ebcd4-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="ebcd4-119">Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="ebcd4-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="ebcd4-120">Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="ebcd4-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)