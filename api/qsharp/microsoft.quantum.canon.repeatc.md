---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: efb820411be63352fc09ada2441a9140dd5575f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840247"
---
# <a name="repeatc-operation"></a><span data-ttu-id="c9905-102">RepeatC 操作</span><span class="sxs-lookup"><span data-stu-id="c9905-102">RepeatC operation</span></span>

<span data-ttu-id="c9905-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c9905-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c9905-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9905-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9905-105">以指定的次數重複作業。</span><span class="sxs-lookup"><span data-stu-id="c9905-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="c9905-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c9905-106">Input</span></span>

### <a name="op--tinput--unit--is-ctl"></a><span data-ttu-id="c9905-107">op： ' TInput => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="c9905-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c9905-108">要重複呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="c9905-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="c9905-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9905-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c9905-110">要呼叫的次數 `op` 。</span><span class="sxs-lookup"><span data-stu-id="c9905-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="c9905-111">輸入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="c9905-111">input : 'TInput</span></span>

<span data-ttu-id="c9905-112">要傳遞至的輸入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="c9905-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c9905-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9905-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c9905-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="c9905-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="c9905-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="c9905-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="c9905-116">範例</span><span class="sxs-lookup"><span data-stu-id="c9905-116">Example</span></span>

<span data-ttu-id="c9905-117">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="c9905-117">The following are equivalent:</span></span>

```qsharp
RepeatC(U, 17, target);
(BoundC(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="c9905-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c9905-118">See Also</span></span>

- [<span data-ttu-id="c9905-119">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="c9905-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="c9905-120">Canon. 重複</span><span class="sxs-lookup"><span data-stu-id="c9905-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="c9905-121">Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="c9905-121">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="c9905-122">Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="c9905-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)