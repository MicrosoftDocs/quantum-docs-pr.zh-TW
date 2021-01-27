---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: 則函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846166"
---
# <a name="emptyarray-function"></a><span data-ttu-id="b0b7a-102">則函式</span><span class="sxs-lookup"><span data-stu-id="b0b7a-102">EmptyArray function</span></span>

<span data-ttu-id="b0b7a-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b0b7a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b0b7a-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b0b7a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b0b7a-105">傳回指定類型的空陣列。</span><span class="sxs-lookup"><span data-stu-id="b0b7a-105">Returns the empty array of a given type.</span></span>

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a><span data-ttu-id="b0b7a-106">輸出： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="b0b7a-106">Output : 'TElement[]</span></span>

<span data-ttu-id="b0b7a-107">空的陣列。</span><span class="sxs-lookup"><span data-stu-id="b0b7a-107">The empty array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b0b7a-108">類型參數</span><span class="sxs-lookup"><span data-stu-id="b0b7a-108">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="b0b7a-109">' TElement</span><span class="sxs-lookup"><span data-stu-id="b0b7a-109">'TElement</span></span>

<span data-ttu-id="b0b7a-110">陣列的元素類型。</span><span class="sxs-lookup"><span data-stu-id="b0b7a-110">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="b0b7a-111">範例</span><span class="sxs-lookup"><span data-stu-id="b0b7a-111">Example</span></span>

```qsharp
let empty = EmptyArray<Int>();
```