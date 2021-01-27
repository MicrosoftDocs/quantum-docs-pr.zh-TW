---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846234"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="5fa7b-102">CumulativeFolded 函式</span><span class="sxs-lookup"><span data-stu-id="5fa7b-102">CumulativeFolded function</span></span>

<span data-ttu-id="5fa7b-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5fa7b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5fa7b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5fa7b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5fa7b-105">將對應和折迭合併為單一函式</span><span class="sxs-lookup"><span data-stu-id="5fa7b-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="5fa7b-106">描述</span><span class="sxs-lookup"><span data-stu-id="5fa7b-106">Description</span></span>

<span data-ttu-id="5fa7b-107">此函式 `fn` 會從初始狀態開始，透過陣列來逐一查看函式， `state` 並傳回所有的中繼值，而不包含初始狀態。</span><span class="sxs-lookup"><span data-stu-id="5fa7b-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="5fa7b-108">輸入</span><span class="sxs-lookup"><span data-stu-id="5fa7b-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="5fa7b-109">fn： ( ' State，t) -> ' 狀態</span><span class="sxs-lookup"><span data-stu-id="5fa7b-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="5fa7b-110">要在陣列上折迭的函式</span><span class="sxs-lookup"><span data-stu-id="5fa7b-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="5fa7b-111">狀態： ' State</span><span class="sxs-lookup"><span data-stu-id="5fa7b-111">state : 'State</span></span>

<span data-ttu-id="5fa7b-112">要折迭的初始狀態</span><span class="sxs-lookup"><span data-stu-id="5fa7b-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="5fa7b-113">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="5fa7b-113">array : 'T[]</span></span>

<span data-ttu-id="5fa7b-114">要折迭的值陣列</span><span class="sxs-lookup"><span data-stu-id="5fa7b-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="5fa7b-115">輸出： ' State []</span><span class="sxs-lookup"><span data-stu-id="5fa7b-115">Output : 'State[]</span></span>

<span data-ttu-id="5fa7b-116">所有中繼狀態，包括最終狀態，但不包含初始狀態。</span><span class="sxs-lookup"><span data-stu-id="5fa7b-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="5fa7b-117">輸出陣列的長度與相同 `array` 。</span><span class="sxs-lookup"><span data-stu-id="5fa7b-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5fa7b-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="5fa7b-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="5fa7b-119">' 狀態</span><span class="sxs-lookup"><span data-stu-id="5fa7b-119">'State</span></span>

<span data-ttu-id="5fa7b-120">函式運作的狀態類型 `fn` ，也就是接受它的第一個輸入並傳回。</span><span class="sxs-lookup"><span data-stu-id="5fa7b-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="5fa7b-121">不要</span><span class="sxs-lookup"><span data-stu-id="5fa7b-121">'T</span></span>

<span data-ttu-id="5fa7b-122">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="5fa7b-122">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="5fa7b-123">範例</span><span class="sxs-lookup"><span data-stu-id="5fa7b-123">Example</span></span>

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```