---
uid: Microsoft.Quantum.Logical.Conditioned
title: 條件式函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198481"
---
# <a name="conditioned-function"></a><span data-ttu-id="37842-102">條件式函數</span><span class="sxs-lookup"><span data-stu-id="37842-102">Conditioned function</span></span>

<span data-ttu-id="37842-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="37842-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="37842-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37842-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37842-105">根據布林值條件的值，傳回兩個值的其中一個。</span><span class="sxs-lookup"><span data-stu-id="37842-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="37842-106">輸入</span><span class="sxs-lookup"><span data-stu-id="37842-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="37842-107">條件： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="37842-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="37842-108">用來控制傳回之輸入的條件。</span><span class="sxs-lookup"><span data-stu-id="37842-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="37842-109">ifTrue： t</span><span class="sxs-lookup"><span data-stu-id="37842-109">ifTrue : 'T</span></span>

<span data-ttu-id="37842-110">當為時要傳回的 `condition` 值 `true` 。</span><span class="sxs-lookup"><span data-stu-id="37842-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="37842-111">ifFalse： t</span><span class="sxs-lookup"><span data-stu-id="37842-111">ifFalse : 'T</span></span>

<span data-ttu-id="37842-112">當為時要傳回的 `condition` 值 `false` 。</span><span class="sxs-lookup"><span data-stu-id="37842-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="37842-113">輸出： t</span><span class="sxs-lookup"><span data-stu-id="37842-113">Output : 'T</span></span>

<span data-ttu-id="37842-114">`ifTrue` 如果 `condition` 為 `true` ，則為， `ifFalse` 否則為。</span><span class="sxs-lookup"><span data-stu-id="37842-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="37842-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="37842-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="37842-116">不要</span><span class="sxs-lookup"><span data-stu-id="37842-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="37842-117">備註</span><span class="sxs-lookup"><span data-stu-id="37842-117">Remarks</span></span>

<span data-ttu-id="37842-118">與運算子不同的 `?|` 是，此函式不會進行較短的運算，因此會完全評估這兩個輸入。</span><span class="sxs-lookup"><span data-stu-id="37842-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="37842-119">最高的最小運算行為，如下所示：</span><span class="sxs-lookup"><span data-stu-id="37842-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```