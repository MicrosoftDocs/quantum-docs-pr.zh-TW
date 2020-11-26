---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: ApplyWithInputTransformationA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 8d65af33a0bc8ce3c08da54b34e68b4e22b710ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207882"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="f24ee-102">ApplyWithInputTransformationA 操作</span><span class="sxs-lookup"><span data-stu-id="f24ee-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="f24ee-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f24ee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f24ee-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f24ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f24ee-105">假設有接受一些輸入的作業，傳回與該作業相容之輸出的函式，以及該函式的輸入，則會使用函式來套用作業，以將輸入轉換成作業預期的表單。</span><span class="sxs-lookup"><span data-stu-id="f24ee-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="f24ee-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f24ee-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="f24ee-107">fn： ' U-> t</span><span class="sxs-lookup"><span data-stu-id="f24ee-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="f24ee-108">將指定輸入轉換成作業預期格式的函式。</span><span class="sxs-lookup"><span data-stu-id="f24ee-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="f24ee-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="f24ee-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f24ee-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="f24ee-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="f24ee-111">輸入： ' U</span><span class="sxs-lookup"><span data-stu-id="f24ee-111">input : 'U</span></span>

<span data-ttu-id="f24ee-112">函數的輸入。</span><span class="sxs-lookup"><span data-stu-id="f24ee-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f24ee-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f24ee-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f24ee-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="f24ee-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f24ee-115">不要</span><span class="sxs-lookup"><span data-stu-id="f24ee-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="f24ee-116">' U</span><span class="sxs-lookup"><span data-stu-id="f24ee-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="f24ee-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f24ee-117">See Also</span></span>

- [<span data-ttu-id="f24ee-118">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="f24ee-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="f24ee-119">Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="f24ee-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="f24ee-120">Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="f24ee-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="f24ee-121">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="f24ee-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)