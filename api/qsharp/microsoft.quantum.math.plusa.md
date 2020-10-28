---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697190"
---
# <a name="plusa-function"></a><span data-ttu-id="63059-102">PlusA 函式</span><span class="sxs-lookup"><span data-stu-id="63059-102">PlusA function</span></span>

<span data-ttu-id="63059-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="63059-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="63059-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63059-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63059-105">傳回兩個輸入 (串連) 的總和。</span><span class="sxs-lookup"><span data-stu-id="63059-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="63059-106">輸入</span><span class="sxs-lookup"><span data-stu-id="63059-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="63059-107">a： ' Element []</span><span class="sxs-lookup"><span data-stu-id="63059-107">a : 'Element[]</span></span>

<span data-ttu-id="63059-108">要加總的第一個輸入 $a $。</span><span class="sxs-lookup"><span data-stu-id="63059-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="63059-109">b： ' Element []</span><span class="sxs-lookup"><span data-stu-id="63059-109">b : 'Element[]</span></span>

<span data-ttu-id="63059-110">第二個輸入 $b $ 以加總。</span><span class="sxs-lookup"><span data-stu-id="63059-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="63059-111">Output： ' Element []</span><span class="sxs-lookup"><span data-stu-id="63059-111">Output : 'Element[]</span></span>

<span data-ttu-id="63059-112">Sum $a + b $。</span><span class="sxs-lookup"><span data-stu-id="63059-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="63059-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="63059-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="63059-114">' 元素</span><span class="sxs-lookup"><span data-stu-id="63059-114">'Element</span></span>

<span data-ttu-id="63059-115">這兩個輸入陣列中每個元素的型別。</span><span class="sxs-lookup"><span data-stu-id="63059-115">The type of each element in each of the two input arrays.</span></span>