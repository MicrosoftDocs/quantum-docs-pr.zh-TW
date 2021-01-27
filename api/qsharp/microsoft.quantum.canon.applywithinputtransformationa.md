---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: ApplyWithInputTransformationA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3ab07f301f310e3ec380981bdb53201fc74bd289
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841132"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="40797-102">ApplyWithInputTransformationA 操作</span><span class="sxs-lookup"><span data-stu-id="40797-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="40797-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="40797-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="40797-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40797-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="40797-105">假設有接受一些輸入的作業，傳回與該作業相容之輸出的函式，以及該函式的輸入，則會使用函式來套用作業，以將輸入轉換成作業預期的表單。</span><span class="sxs-lookup"><span data-stu-id="40797-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="40797-106">輸入</span><span class="sxs-lookup"><span data-stu-id="40797-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="40797-107">fn： ' U-> t</span><span class="sxs-lookup"><span data-stu-id="40797-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="40797-108">將指定輸入轉換成作業預期格式的函式。</span><span class="sxs-lookup"><span data-stu-id="40797-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="40797-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="40797-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="40797-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="40797-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="40797-111">輸入： ' U</span><span class="sxs-lookup"><span data-stu-id="40797-111">input : 'U</span></span>

<span data-ttu-id="40797-112">函數的輸入。</span><span class="sxs-lookup"><span data-stu-id="40797-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="40797-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40797-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="40797-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="40797-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="40797-115">不要</span><span class="sxs-lookup"><span data-stu-id="40797-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="40797-116">' U</span><span class="sxs-lookup"><span data-stu-id="40797-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="40797-117">範例</span><span class="sxs-lookup"><span data-stu-id="40797-117">Example</span></span>

<span data-ttu-id="40797-118">下列呼叫會使用 @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" ，將針對輸入輸入的作業套用 @"Microsoft.Quantum.Arithmetic.BigEndian" 至類型的輸入 @"Microsoft.Quantum.Arithmetic.LittleEndian" ：</span><span class="sxs-lookup"><span data-stu-id="40797-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="40797-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="40797-119">See Also</span></span>

- [<span data-ttu-id="40797-120">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="40797-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="40797-121">Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="40797-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="40797-122">Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="40797-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="40797-123">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="40797-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)