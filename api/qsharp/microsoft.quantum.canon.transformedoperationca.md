---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 21c9cdfc3b5b266cb3b93e52ee2fa4c655caf795
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698822"
---
# <a name="transformedoperationca-function"></a><span data-ttu-id="a61fa-102">TransformedOperationCA 函式</span><span class="sxs-lookup"><span data-stu-id="a61fa-102">TransformedOperationCA function</span></span>

<span data-ttu-id="a61fa-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a61fa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a61fa-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a61fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a61fa-105">指定函式和作業之後，會傳回新的作業，其輸入會由指定的函式進行轉換。</span><span class="sxs-lookup"><span data-stu-id="a61fa-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="a61fa-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a61fa-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="a61fa-107">fn： ' U-> t</span><span class="sxs-lookup"><span data-stu-id="a61fa-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="a61fa-108">將指定輸入轉換成作業預期格式的函式。</span><span class="sxs-lookup"><span data-stu-id="a61fa-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="a61fa-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a61fa-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a61fa-110">要轉換的作業。</span><span class="sxs-lookup"><span data-stu-id="a61fa-110">The operation to be transformed.</span></span>



## <a name="output--u--unit-adj--ctl"></a><span data-ttu-id="a61fa-111">輸出： ' U => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a61fa-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a61fa-112">新的作業會 tbat 呼叫與其 `fn` 輸入，然後將產生的輸出傳遞給 `op` 。</span><span class="sxs-lookup"><span data-stu-id="a61fa-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a61fa-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="a61fa-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a61fa-114">不要</span><span class="sxs-lookup"><span data-stu-id="a61fa-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="a61fa-115">' U</span><span class="sxs-lookup"><span data-stu-id="a61fa-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="a61fa-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a61fa-116">See Also</span></span>

- [<span data-ttu-id="a61fa-117">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="a61fa-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="a61fa-118">Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="a61fa-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="a61fa-119">Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="a61fa-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="a61fa-120">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="a61fa-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="a61fa-121">Canon 組成</span><span class="sxs-lookup"><span data-stu-id="a61fa-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)