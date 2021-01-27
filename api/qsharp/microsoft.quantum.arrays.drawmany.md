---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846211"
---
# <a name="drawmany-operation"></a><span data-ttu-id="68cdb-102">DrawMany 操作</span><span class="sxs-lookup"><span data-stu-id="68cdb-102">DrawMany operation</span></span>

<span data-ttu-id="68cdb-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="68cdb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="68cdb-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68cdb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68cdb-105">針對指定的樣本數重複作業，並在陣列中收集其輸出。</span><span class="sxs-lookup"><span data-stu-id="68cdb-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="68cdb-106">輸入</span><span class="sxs-lookup"><span data-stu-id="68cdb-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="68cdb-107">op： ' TInput => ' Toutput></span><span class="sxs-lookup"><span data-stu-id="68cdb-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="68cdb-108">要重複呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="68cdb-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="68cdb-109">nSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="68cdb-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="68cdb-110">要收集的呼叫樣本數 `op` 。</span><span class="sxs-lookup"><span data-stu-id="68cdb-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="68cdb-111">輸入： ' TInput</span><span class="sxs-lookup"><span data-stu-id="68cdb-111">input : 'TInput</span></span>

<span data-ttu-id="68cdb-112">要傳遞至的輸入 `op` 。</span><span class="sxs-lookup"><span data-stu-id="68cdb-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="68cdb-113">輸出： ' Toutput> []</span><span class="sxs-lookup"><span data-stu-id="68cdb-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="68cdb-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="68cdb-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="68cdb-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="68cdb-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="68cdb-116">' Toutput></span><span class="sxs-lookup"><span data-stu-id="68cdb-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="68cdb-117">範例</span><span class="sxs-lookup"><span data-stu-id="68cdb-117">Example</span></span>

<span data-ttu-id="68cdb-118">下列範例會在指定一次取樣一個位的作業時，提供一個整數。</span><span class="sxs-lookup"><span data-stu-id="68cdb-118">The following samples an integer, given an operation that samples a single bit at a time.</span></span>

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a><span data-ttu-id="68cdb-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="68cdb-119">See Also</span></span>

- [<span data-ttu-id="68cdb-120">Canon. 重複</span><span class="sxs-lookup"><span data-stu-id="68cdb-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)