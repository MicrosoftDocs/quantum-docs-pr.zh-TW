---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699411"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="e2bf8-102">TupleArrayAsNestedArray 函式</span><span class="sxs-lookup"><span data-stu-id="e2bf8-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="e2bf8-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e2bf8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e2bf8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e2bf8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e2bf8-105">將2元組的清單轉換成嵌套陣列。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="e2bf8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e2bf8-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="e2bf8-107">tupleList： ( t，t) []</span><span class="sxs-lookup"><span data-stu-id="e2bf8-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="e2bf8-108">要轉換成嵌套陣列的2個元組清單。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="e2bf8-109">Output： t [] []</span><span class="sxs-lookup"><span data-stu-id="e2bf8-109">Output : 'T[][]</span></span>

<span data-ttu-id="e2bf8-110">長度符合 tupleList 的嵌套陣列。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="e2bf8-111">範例</span><span class="sxs-lookup"><span data-stu-id="e2bf8-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="e2bf8-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="e2bf8-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e2bf8-113">不要</span><span class="sxs-lookup"><span data-stu-id="e2bf8-113">'T</span></span>

