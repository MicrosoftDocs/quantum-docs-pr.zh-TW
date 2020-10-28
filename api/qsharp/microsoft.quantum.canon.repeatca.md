---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: b68c3aa4298fffa76f7c43ac4c6d27cdf3b72fbf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698887"
---
# <a name="repeatca-operation"></a><span data-ttu-id="998c5-102">RepeatCA 操作</span><span class="sxs-lookup"><span data-stu-id="998c5-102">RepeatCA operation</span></span>

<span data-ttu-id="998c5-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="998c5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="998c5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="998c5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="998c5-105">以指定的次數重複作業。</span><span class="sxs-lookup"><span data-stu-id="998c5-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="998c5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="998c5-106">Input</span></span>

### <a name="op--tinput--unit-adj--ctl"></a><span data-ttu-id="998c5-107">op： ' TInput => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="998c5-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="998c5-108">要重複呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="998c5-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="998c5-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="998c5-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="998c5-110">要呼叫的次數 `op` 。</span><span class="sxs-lookup"><span data-stu-id="998c5-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="998c5-111">輸入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="998c5-111">input : 'TInput</span></span>

<span data-ttu-id="998c5-112">要傳遞至的輸入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="998c5-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="998c5-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="998c5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="998c5-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="998c5-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="998c5-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="998c5-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="998c5-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="998c5-116">See Also</span></span>

- [<span data-ttu-id="998c5-117">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="998c5-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="998c5-118">Canon. 重複</span><span class="sxs-lookup"><span data-stu-id="998c5-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="998c5-119">Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="998c5-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="998c5-120">Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="998c5-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)