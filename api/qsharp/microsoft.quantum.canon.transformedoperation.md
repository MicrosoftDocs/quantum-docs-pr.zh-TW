---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: a26cc178f67fd99324355ac230d9e91081b6e238
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204924"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="3bac8-102">TransformedOperation 函式</span><span class="sxs-lookup"><span data-stu-id="3bac8-102">TransformedOperation function</span></span>

<span data-ttu-id="3bac8-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3bac8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3bac8-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3bac8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3bac8-105">指定函式和作業之後，會傳回新的作業，其輸入會由指定的函式進行轉換。</span><span class="sxs-lookup"><span data-stu-id="3bac8-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="3bac8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="3bac8-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="3bac8-107">fn： ' U-> t</span><span class="sxs-lookup"><span data-stu-id="3bac8-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="3bac8-108">將指定輸入轉換成作業預期格式的函式。</span><span class="sxs-lookup"><span data-stu-id="3bac8-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="3bac8-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3bac8-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3bac8-110">要轉換的作業。</span><span class="sxs-lookup"><span data-stu-id="3bac8-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="3bac8-111">輸出： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3bac8-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3bac8-112">新的作業會 tbat 呼叫與其 `fn` 輸入，然後將產生的輸出傳遞給 `op` 。</span><span class="sxs-lookup"><span data-stu-id="3bac8-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3bac8-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="3bac8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3bac8-114">不要</span><span class="sxs-lookup"><span data-stu-id="3bac8-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="3bac8-115">' U</span><span class="sxs-lookup"><span data-stu-id="3bac8-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="3bac8-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3bac8-116">See Also</span></span>

- [<span data-ttu-id="3bac8-117">Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="3bac8-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="3bac8-118">Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="3bac8-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="3bac8-119">Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="3bac8-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="3bac8-120">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="3bac8-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="3bac8-121">Canon 組成</span><span class="sxs-lookup"><span data-stu-id="3bac8-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)