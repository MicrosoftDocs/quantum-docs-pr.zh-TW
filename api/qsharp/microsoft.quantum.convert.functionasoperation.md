---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224372"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="f4cb1-102">FunctionAsOperation 函式</span><span class="sxs-lookup"><span data-stu-id="f4cb1-102">FunctionAsOperation function</span></span>

<span data-ttu-id="f4cb1-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="f4cb1-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="f4cb1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4cb1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4cb1-105">將函數轉換成作業。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="f4cb1-106">描述</span><span class="sxs-lookup"><span data-stu-id="f4cb1-106">Description</span></span>

<span data-ttu-id="f4cb1-107">指定函式時，會傳回呼叫該函式，而不會執行其他動作的作業。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="f4cb1-108">輸入</span><span class="sxs-lookup"><span data-stu-id="f4cb1-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="f4cb1-109">fn： ' Input-> ' 輸出</span><span class="sxs-lookup"><span data-stu-id="f4cb1-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="f4cb1-110">要轉換成運算的函式。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="f4cb1-111">輸出： ' Input => ' 輸出</span><span class="sxs-lookup"><span data-stu-id="f4cb1-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="f4cb1-112">與 `op` `op(input)` 全部相同的作業 `fn(input)` `input` 。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f4cb1-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="f4cb1-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="f4cb1-114">' 輸入</span><span class="sxs-lookup"><span data-stu-id="f4cb1-114">'Input</span></span>

<span data-ttu-id="f4cb1-115">要轉換之函數的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="f4cb1-116">' 輸出</span><span class="sxs-lookup"><span data-stu-id="f4cb1-116">'Output</span></span>

<span data-ttu-id="f4cb1-117">要轉換之函數的輸出類型。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4cb1-118">備註</span><span class="sxs-lookup"><span data-stu-id="f4cb1-118">Remarks</span></span>

<span data-ttu-id="f4cb1-119">這項功能主要適用于將函式傳遞至預期作業為輸入的函式或作業。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>