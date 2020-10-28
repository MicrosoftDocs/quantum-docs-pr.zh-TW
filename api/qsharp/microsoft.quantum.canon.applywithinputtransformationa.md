---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: ApplyWithInputTransformationA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b72c131691e08b4bd32b7faf9265aad6c52b7fde
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699117"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="68e72-102">ApplyWithInputTransformationA 操作</span><span class="sxs-lookup"><span data-stu-id="68e72-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="68e72-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="68e72-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="68e72-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="68e72-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="68e72-105">假設有接受一些輸入的作業，傳回與該作業相容之輸出的函式，以及該函式的輸入，則會使用函式來套用作業，以將輸入轉換成作業預期的表單。</span><span class="sxs-lookup"><span data-stu-id="68e72-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="68e72-106">輸入</span><span class="sxs-lookup"><span data-stu-id="68e72-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="68e72-107">fn： ' U-> t</span><span class="sxs-lookup"><span data-stu-id="68e72-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="68e72-108">將指定輸入轉換成作業預期格式的函式。</span><span class="sxs-lookup"><span data-stu-id="68e72-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="68e72-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="68e72-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="68e72-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="68e72-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="68e72-111">輸入： ' U</span><span class="sxs-lookup"><span data-stu-id="68e72-111">input : 'U</span></span>

<span data-ttu-id="68e72-112">函數的輸入。</span><span class="sxs-lookup"><span data-stu-id="68e72-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="68e72-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="68e72-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="68e72-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="68e72-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="68e72-115">不要</span><span class="sxs-lookup"><span data-stu-id="68e72-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="68e72-116">' U</span><span class="sxs-lookup"><span data-stu-id="68e72-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="68e72-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="68e72-117">See Also</span></span>

- [<span data-ttu-id="68e72-118">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="68e72-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="68e72-119">Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="68e72-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="68e72-120">Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="68e72-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="68e72-121">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="68e72-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)