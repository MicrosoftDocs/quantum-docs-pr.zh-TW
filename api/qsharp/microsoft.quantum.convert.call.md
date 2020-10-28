---
uid: Microsoft.Quantum.Convert.Call
title: 呼叫作業
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698311"
---
# <a name="call-operation"></a><span data-ttu-id="e148e-102">呼叫作業</span><span class="sxs-lookup"><span data-stu-id="e148e-102">Call operation</span></span>

<span data-ttu-id="e148e-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e148e-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e148e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e148e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e148e-105">使用指定的輸入呼叫函數。</span><span class="sxs-lookup"><span data-stu-id="e148e-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="e148e-106">描述</span><span class="sxs-lookup"><span data-stu-id="e148e-106">Description</span></span>

<span data-ttu-id="e148e-107">假設函式和該函式的輸入，則會呼叫函式並傳回其輸出。</span><span class="sxs-lookup"><span data-stu-id="e148e-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="e148e-108">輸入</span><span class="sxs-lookup"><span data-stu-id="e148e-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="e148e-109">fn： ' Input-> ' 輸出</span><span class="sxs-lookup"><span data-stu-id="e148e-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="e148e-110">要呼叫的函式。</span><span class="sxs-lookup"><span data-stu-id="e148e-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="e148e-111">輸入： ' Input</span><span class="sxs-lookup"><span data-stu-id="e148e-111">input : 'Input</span></span>

<span data-ttu-id="e148e-112">要傳遞至函數的輸入。</span><span class="sxs-lookup"><span data-stu-id="e148e-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="e148e-113">輸出： ' Output</span><span class="sxs-lookup"><span data-stu-id="e148e-113">Output : 'Output</span></span>

<span data-ttu-id="e148e-114">呼叫 `fn` 的結果。</span><span class="sxs-lookup"><span data-stu-id="e148e-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e148e-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="e148e-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="e148e-116">' 輸入</span><span class="sxs-lookup"><span data-stu-id="e148e-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="e148e-117">' 輸出</span><span class="sxs-lookup"><span data-stu-id="e148e-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="e148e-118">備註</span><span class="sxs-lookup"><span data-stu-id="e148e-118">Remarks</span></span>

<span data-ttu-id="e148e-119">這項作業主要適合用來強制在作業內的特定位置呼叫函式，或在需要作業的情況下呼叫函數。</span><span class="sxs-lookup"><span data-stu-id="e148e-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>