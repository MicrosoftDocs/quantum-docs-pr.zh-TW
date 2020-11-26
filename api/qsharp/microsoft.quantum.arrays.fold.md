---
uid: Microsoft.Quantum.Arrays.Fold
title: 折迭函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: a42f9a832c18bd612c1ae416187f3f2513eed54d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221159"
---
# <a name="fold-function"></a><span data-ttu-id="f0290-102">折迭函數</span><span class="sxs-lookup"><span data-stu-id="f0290-102">Fold function</span></span>

<span data-ttu-id="f0290-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f0290-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f0290-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0290-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0290-105">`f`透過陣列逐一查看函式 `array` ，傳回 `f(f(f(initialState, array[0]), array[1]), ...)` 。</span><span class="sxs-lookup"><span data-stu-id="f0290-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="f0290-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f0290-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="f0290-107">資料夾： ( ' 狀態，不) -> ' 狀態</span><span class="sxs-lookup"><span data-stu-id="f0290-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="f0290-108">要在陣列上折迭的函式。</span><span class="sxs-lookup"><span data-stu-id="f0290-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="f0290-109">狀態： ' State</span><span class="sxs-lookup"><span data-stu-id="f0290-109">state : 'State</span></span>

<span data-ttu-id="f0290-110">資料夾的初始狀態。</span><span class="sxs-lookup"><span data-stu-id="f0290-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="f0290-111">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="f0290-111">array : 'T[]</span></span>

<span data-ttu-id="f0290-112">要折迭的值陣列。</span><span class="sxs-lookup"><span data-stu-id="f0290-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="f0290-113">輸出： ' 狀態</span><span class="sxs-lookup"><span data-stu-id="f0290-113">Output : 'State</span></span>

<span data-ttu-id="f0290-114">在逐一查看的所有專案之後，資料夾所傳回的最終狀態 `array` 。</span><span class="sxs-lookup"><span data-stu-id="f0290-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f0290-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="f0290-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="f0290-116">' 狀態</span><span class="sxs-lookup"><span data-stu-id="f0290-116">'State</span></span>

<span data-ttu-id="f0290-117">函式運作的狀態類型 `folder` ，也就是接受作為其第一個引數並傳回。</span><span class="sxs-lookup"><span data-stu-id="f0290-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="f0290-118">不要</span><span class="sxs-lookup"><span data-stu-id="f0290-118">'T</span></span>

<span data-ttu-id="f0290-119">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="f0290-119">The type of `array` elements.</span></span>