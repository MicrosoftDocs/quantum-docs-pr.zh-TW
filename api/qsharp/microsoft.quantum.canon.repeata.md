---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 89d34e5a30a61dee392904ce1076605432e21395
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698891"
---
# <a name="repeata-operation"></a><span data-ttu-id="f0128-102">RepeatA 操作</span><span class="sxs-lookup"><span data-stu-id="f0128-102">RepeatA operation</span></span>

<span data-ttu-id="f0128-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f0128-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f0128-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f0128-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f0128-105">以指定的次數重複作業。</span><span class="sxs-lookup"><span data-stu-id="f0128-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="f0128-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f0128-106">Input</span></span>

### <a name="op--tinput--unit-adj"></a><span data-ttu-id="f0128-107">op： ' TInput => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="f0128-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f0128-108">要重複呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="f0128-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="f0128-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f0128-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f0128-110">要呼叫的次數 `op` 。</span><span class="sxs-lookup"><span data-stu-id="f0128-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="f0128-111">輸入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="f0128-111">input : 'TInput</span></span>

<span data-ttu-id="f0128-112">要傳遞至的輸入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="f0128-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f0128-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f0128-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f0128-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="f0128-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="f0128-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="f0128-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="f0128-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f0128-116">See Also</span></span>

- [<span data-ttu-id="f0128-117">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="f0128-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="f0128-118">Canon. 重複</span><span class="sxs-lookup"><span data-stu-id="f0128-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="f0128-119">Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="f0128-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="f0128-120">Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="f0128-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)