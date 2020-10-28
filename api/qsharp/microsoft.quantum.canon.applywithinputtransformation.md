---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: ApplyWithInputTransformation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 2b7863337ef724d9c3ba10201a9a01d0b2226ea8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699119"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="d0ee7-102">ApplyWithInputTransformation 操作</span><span class="sxs-lookup"><span data-stu-id="d0ee7-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="d0ee7-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d0ee7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d0ee7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0ee7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0ee7-105">假設有接受一些輸入的作業，傳回與該作業相容之輸出的函式，以及該函式的輸入，則會使用函式來套用作業，以將輸入轉換成作業預期的表單。</span><span class="sxs-lookup"><span data-stu-id="d0ee7-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="d0ee7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d0ee7-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="d0ee7-107">fn： ' U-> t</span><span class="sxs-lookup"><span data-stu-id="d0ee7-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="d0ee7-108">將指定輸入轉換成作業預期格式的函式。</span><span class="sxs-lookup"><span data-stu-id="d0ee7-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="d0ee7-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0ee7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d0ee7-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="d0ee7-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="d0ee7-111">輸入： ' U</span><span class="sxs-lookup"><span data-stu-id="d0ee7-111">input : 'U</span></span>

<span data-ttu-id="d0ee7-112">函數的輸入。</span><span class="sxs-lookup"><span data-stu-id="d0ee7-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0ee7-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0ee7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d0ee7-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="d0ee7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0ee7-115">不要</span><span class="sxs-lookup"><span data-stu-id="d0ee7-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="d0ee7-116">' U</span><span class="sxs-lookup"><span data-stu-id="d0ee7-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="d0ee7-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d0ee7-117">See Also</span></span>

- [<span data-ttu-id="d0ee7-118">Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="d0ee7-118">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="d0ee7-119">Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="d0ee7-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="d0ee7-120">Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="d0ee7-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="d0ee7-121">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="d0ee7-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)