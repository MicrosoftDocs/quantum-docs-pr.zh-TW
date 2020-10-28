---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698306"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="e0dfd-102">FunctionAsOperation 函式</span><span class="sxs-lookup"><span data-stu-id="e0dfd-102">FunctionAsOperation function</span></span>

<span data-ttu-id="e0dfd-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e0dfd-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e0dfd-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e0dfd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e0dfd-105">將函數轉換成作業。</span><span class="sxs-lookup"><span data-stu-id="e0dfd-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="e0dfd-106">描述</span><span class="sxs-lookup"><span data-stu-id="e0dfd-106">Description</span></span>

<span data-ttu-id="e0dfd-107">指定函式時，會傳回呼叫該函式，而不會執行其他動作的作業。</span><span class="sxs-lookup"><span data-stu-id="e0dfd-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="e0dfd-108">輸入</span><span class="sxs-lookup"><span data-stu-id="e0dfd-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="e0dfd-109">fn： ' Input-> ' 輸出</span><span class="sxs-lookup"><span data-stu-id="e0dfd-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="e0dfd-110">要轉換成運算的函式。</span><span class="sxs-lookup"><span data-stu-id="e0dfd-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="e0dfd-111">輸出： ' Input => ' 輸出</span><span class="sxs-lookup"><span data-stu-id="e0dfd-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="e0dfd-112">與 `op` `op(input)` 全部相同的作業 `fn(input)` `input` 。</span><span class="sxs-lookup"><span data-stu-id="e0dfd-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e0dfd-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="e0dfd-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="e0dfd-114">' 輸入</span><span class="sxs-lookup"><span data-stu-id="e0dfd-114">'Input</span></span>

<span data-ttu-id="e0dfd-115">要轉換之函數的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="e0dfd-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="e0dfd-116">' 輸出</span><span class="sxs-lookup"><span data-stu-id="e0dfd-116">'Output</span></span>

<span data-ttu-id="e0dfd-117">要轉換之函數的輸出類型。</span><span class="sxs-lookup"><span data-stu-id="e0dfd-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0dfd-118">備註</span><span class="sxs-lookup"><span data-stu-id="e0dfd-118">Remarks</span></span>

<span data-ttu-id="e0dfd-119">這項功能主要適用于將函式傳遞至預期作業為輸入的函式或作業。</span><span class="sxs-lookup"><span data-stu-id="e0dfd-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>