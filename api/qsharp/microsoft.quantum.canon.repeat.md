---
uid: Microsoft.Quantum.Canon.Repeat
title: 重複操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5aedd056b851b8d8d7c25a32eb22587292e132a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698902"
---
# <a name="repeat-operation"></a><span data-ttu-id="826f0-102">重複操作</span><span class="sxs-lookup"><span data-stu-id="826f0-102">Repeat operation</span></span>

<span data-ttu-id="826f0-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="826f0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="826f0-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="826f0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="826f0-105">以指定的次數重複作業。</span><span class="sxs-lookup"><span data-stu-id="826f0-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="826f0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="826f0-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="826f0-107">op： ' TInput => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="826f0-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="826f0-108">要重複呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="826f0-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="826f0-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="826f0-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="826f0-110">要呼叫的次數 `op` 。</span><span class="sxs-lookup"><span data-stu-id="826f0-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="826f0-111">輸入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="826f0-111">input : 'TInput</span></span>

<span data-ttu-id="826f0-112">要傳遞至的輸入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="826f0-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="826f0-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="826f0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="826f0-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="826f0-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="826f0-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="826f0-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="826f0-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="826f0-116">See Also</span></span>

- [<span data-ttu-id="826f0-117">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="826f0-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="826f0-118">Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="826f0-118">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="826f0-119">Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="826f0-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="826f0-120">Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="826f0-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)