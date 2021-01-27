---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: af93220562d6be27b2f41e770bd953e5e808fcbf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852215"
---
# <a name="repeatca-operation"></a><span data-ttu-id="086df-102">RepeatCA 操作</span><span class="sxs-lookup"><span data-stu-id="086df-102">RepeatCA operation</span></span>

<span data-ttu-id="086df-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="086df-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="086df-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="086df-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="086df-105">以指定的次數重複作業。</span><span class="sxs-lookup"><span data-stu-id="086df-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="086df-106">輸入</span><span class="sxs-lookup"><span data-stu-id="086df-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="086df-107">op： ' TInput => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="086df-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="086df-108">要重複呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="086df-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="086df-109">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="086df-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="086df-110">要呼叫的次數 `op` 。</span><span class="sxs-lookup"><span data-stu-id="086df-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="086df-111">輸入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="086df-111">input : 'TInput</span></span>

<span data-ttu-id="086df-112">要傳遞至的輸入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="086df-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="086df-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="086df-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="086df-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="086df-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="086df-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="086df-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="086df-116">範例</span><span class="sxs-lookup"><span data-stu-id="086df-116">Example</span></span>

<span data-ttu-id="086df-117">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="086df-117">The following are equivalent:</span></span>

```qsharp
RepeatCA(U, 17, target);
(BoundCA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="086df-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="086df-118">See Also</span></span>

- [<span data-ttu-id="086df-119">DrawMany。</span><span class="sxs-lookup"><span data-stu-id="086df-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="086df-120">Canon. 重複</span><span class="sxs-lookup"><span data-stu-id="086df-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="086df-121">Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="086df-121">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="086df-122">Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="086df-122">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)