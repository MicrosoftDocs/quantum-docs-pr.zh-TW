---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699505"
---
# <a name="drawmany-operation"></a><span data-ttu-id="a894c-102">DrawMany 操作</span><span class="sxs-lookup"><span data-stu-id="a894c-102">DrawMany operation</span></span>

<span data-ttu-id="a894c-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a894c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a894c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a894c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a894c-105">針對指定的樣本數重複作業，並在陣列中收集其輸出。</span><span class="sxs-lookup"><span data-stu-id="a894c-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="a894c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a894c-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="a894c-107">op： ' TInput => ' Toutput></span><span class="sxs-lookup"><span data-stu-id="a894c-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="a894c-108">要重複呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="a894c-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="a894c-109">nSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a894c-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a894c-110">要收集的呼叫樣本數 `op` 。</span><span class="sxs-lookup"><span data-stu-id="a894c-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="a894c-111">輸入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="a894c-111">input : 'TInput</span></span>

<span data-ttu-id="a894c-112">要傳遞至的輸入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="a894c-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="a894c-113">輸出： ' Toutput> []</span><span class="sxs-lookup"><span data-stu-id="a894c-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a894c-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="a894c-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="a894c-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="a894c-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="a894c-116">' Toutput></span><span class="sxs-lookup"><span data-stu-id="a894c-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="a894c-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a894c-117">See Also</span></span>

- [<span data-ttu-id="a894c-118">Canon. 重複</span><span class="sxs-lookup"><span data-stu-id="a894c-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)