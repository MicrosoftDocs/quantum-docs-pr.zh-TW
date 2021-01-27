---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: ApplyWithInputTransformationC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d877fedbc0caa1a9ebc87d80cbce9ab54ca20d88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850363"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="1c231-102">ApplyWithInputTransformationC 操作</span><span class="sxs-lookup"><span data-stu-id="1c231-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="1c231-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1c231-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1c231-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1c231-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1c231-105">假設有接受一些輸入的作業，傳回與該作業相容之輸出的函式，以及該函式的輸入，則會使用函式來套用作業，以將輸入轉換成作業預期的表單。</span><span class="sxs-lookup"><span data-stu-id="1c231-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="1c231-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1c231-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="1c231-107">fn： ' U-> t</span><span class="sxs-lookup"><span data-stu-id="1c231-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="1c231-108">將指定輸入轉換成作業預期格式的函式。</span><span class="sxs-lookup"><span data-stu-id="1c231-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="1c231-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="1c231-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1c231-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="1c231-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="1c231-111">輸入： ' U</span><span class="sxs-lookup"><span data-stu-id="1c231-111">input : 'U</span></span>

<span data-ttu-id="1c231-112">函數的輸入。</span><span class="sxs-lookup"><span data-stu-id="1c231-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c231-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c231-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1c231-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="1c231-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1c231-115">不要</span><span class="sxs-lookup"><span data-stu-id="1c231-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="1c231-116">' U</span><span class="sxs-lookup"><span data-stu-id="1c231-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="1c231-117">範例</span><span class="sxs-lookup"><span data-stu-id="1c231-117">Example</span></span>

<span data-ttu-id="1c231-118">下列呼叫會使用 @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" ，將針對輸入輸入的作業套用 @"Microsoft.Quantum.Arithmetic.BigEndian" 至類型的輸入 @"Microsoft.Quantum.Arithmetic.LittleEndian" ：</span><span class="sxs-lookup"><span data-stu-id="1c231-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="1c231-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1c231-119">See Also</span></span>

- [<span data-ttu-id="1c231-120">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="1c231-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="1c231-121">Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="1c231-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="1c231-122">Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="1c231-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="1c231-123">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="1c231-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)