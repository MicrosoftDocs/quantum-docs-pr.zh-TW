---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fac0fb6e03dc515892783fb4a5fa9cfc274550b8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840133"
---
# <a name="transformedoperationa-function"></a><span data-ttu-id="473bd-102">TransformedOperationA 函式</span><span class="sxs-lookup"><span data-stu-id="473bd-102">TransformedOperationA function</span></span>

<span data-ttu-id="473bd-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="473bd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="473bd-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="473bd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="473bd-105">指定函式和作業之後，會傳回新的作業，其輸入會由指定的函式進行轉換。</span><span class="sxs-lookup"><span data-stu-id="473bd-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="473bd-106">輸入</span><span class="sxs-lookup"><span data-stu-id="473bd-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="473bd-107">fn： ' U-> t</span><span class="sxs-lookup"><span data-stu-id="473bd-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="473bd-108">將指定輸入轉換成作業預期格式的函式。</span><span class="sxs-lookup"><span data-stu-id="473bd-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="473bd-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="473bd-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="473bd-110">要轉換的作業。</span><span class="sxs-lookup"><span data-stu-id="473bd-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj"></a><span data-ttu-id="473bd-111">輸出： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="473bd-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="473bd-112">新的作業會 tbat 呼叫與其 `fn` 輸入，然後將產生的輸出傳遞給 `op` 。</span><span class="sxs-lookup"><span data-stu-id="473bd-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="473bd-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="473bd-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="473bd-114">不要</span><span class="sxs-lookup"><span data-stu-id="473bd-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="473bd-115">' U</span><span class="sxs-lookup"><span data-stu-id="473bd-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="473bd-116">範例</span><span class="sxs-lookup"><span data-stu-id="473bd-116">Example</span></span>

<span data-ttu-id="473bd-117">下列呼叫會使用 @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" 將針對輸入設計的作業轉換為 @"Microsoft.Quantum.Arithmetic.BigEndian" 接受類型輸入的作業 @"Microsoft.Quantum.Arithmetic.LittleEndian" ：</span><span class="sxs-lookup"><span data-stu-id="473bd-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="473bd-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="473bd-118">See Also</span></span>

- [<span data-ttu-id="473bd-119">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="473bd-119">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="473bd-120">Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="473bd-120">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="473bd-121">Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="473bd-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="473bd-122">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="473bd-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="473bd-123">Canon 組成</span><span class="sxs-lookup"><span data-stu-id="473bd-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)