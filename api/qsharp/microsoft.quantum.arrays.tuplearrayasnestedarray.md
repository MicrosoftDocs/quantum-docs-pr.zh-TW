---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 51a35555080d1d2475fc1aa9e48e84c7c6f92c51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845398"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="ac597-102">TupleArrayAsNestedArray 函式</span><span class="sxs-lookup"><span data-stu-id="ac597-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="ac597-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ac597-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ac597-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac597-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac597-105">將2元組的清單轉換成嵌套陣列。</span><span class="sxs-lookup"><span data-stu-id="ac597-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="ac597-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ac597-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="ac597-107">tupleList： ( t，t) []</span><span class="sxs-lookup"><span data-stu-id="ac597-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="ac597-108">要轉換成嵌套陣列的2個元組清單。</span><span class="sxs-lookup"><span data-stu-id="ac597-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="ac597-109">Output： t [] []</span><span class="sxs-lookup"><span data-stu-id="ac597-109">Output : 'T[][]</span></span>

<span data-ttu-id="ac597-110">長度符合 tupleList 的嵌套陣列。</span><span class="sxs-lookup"><span data-stu-id="ac597-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="ac597-111">範例</span><span class="sxs-lookup"><span data-stu-id="ac597-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="ac597-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="ac597-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ac597-113">不要</span><span class="sxs-lookup"><span data-stu-id="ac597-113">'T</span></span>

