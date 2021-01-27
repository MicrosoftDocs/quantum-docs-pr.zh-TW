---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833831"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="18531-102">FunctionAsOperation 函式</span><span class="sxs-lookup"><span data-stu-id="18531-102">FunctionAsOperation function</span></span>

<span data-ttu-id="18531-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="18531-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="18531-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18531-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18531-105">將函數轉換成作業。</span><span class="sxs-lookup"><span data-stu-id="18531-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="18531-106">描述</span><span class="sxs-lookup"><span data-stu-id="18531-106">Description</span></span>

<span data-ttu-id="18531-107">指定函式時，會傳回呼叫該函式，而不會執行其他動作的作業。</span><span class="sxs-lookup"><span data-stu-id="18531-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="18531-108">輸入</span><span class="sxs-lookup"><span data-stu-id="18531-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="18531-109">fn： ' Input-> ' 輸出</span><span class="sxs-lookup"><span data-stu-id="18531-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="18531-110">要轉換成運算的函式。</span><span class="sxs-lookup"><span data-stu-id="18531-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="18531-111">輸出： ' Input => ' 輸出</span><span class="sxs-lookup"><span data-stu-id="18531-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="18531-112">與 `op` `op(input)` 全部相同的作業 `fn(input)` `input` 。</span><span class="sxs-lookup"><span data-stu-id="18531-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="18531-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="18531-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="18531-114">' 輸入</span><span class="sxs-lookup"><span data-stu-id="18531-114">'Input</span></span>

<span data-ttu-id="18531-115">要轉換之函數的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="18531-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="18531-116">' 輸出</span><span class="sxs-lookup"><span data-stu-id="18531-116">'Output</span></span>

<span data-ttu-id="18531-117">要轉換之函數的輸出類型。</span><span class="sxs-lookup"><span data-stu-id="18531-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="18531-118">備註</span><span class="sxs-lookup"><span data-stu-id="18531-118">Remarks</span></span>

<span data-ttu-id="18531-119">這項功能主要適用于將函式傳遞至預期作業為輸入的函式或作業。</span><span class="sxs-lookup"><span data-stu-id="18531-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>