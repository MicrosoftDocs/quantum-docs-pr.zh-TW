---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848517"
---
# <a name="indexof-function"></a><span data-ttu-id="c5d33-102">IndexOf 函式</span><span class="sxs-lookup"><span data-stu-id="c5d33-102">IndexOf function</span></span>

<span data-ttu-id="c5d33-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c5d33-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c5d33-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5d33-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5d33-105">傳回陣列中第一個符合指定之述詞的第一個元素索引。</span><span class="sxs-lookup"><span data-stu-id="c5d33-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="c5d33-106">如果沒有這類元素，則傳回-1。</span><span class="sxs-lookup"><span data-stu-id="c5d33-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="c5d33-107">輸入</span><span class="sxs-lookup"><span data-stu-id="c5d33-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="c5d33-108">述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c5d33-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c5d33-109">在陣列元素上作用的述詞函式。</span><span class="sxs-lookup"><span data-stu-id="c5d33-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="c5d33-110">arr： t []</span><span class="sxs-lookup"><span data-stu-id="c5d33-110">arr : 'T[]</span></span>

<span data-ttu-id="c5d33-111">要使用指定述詞搜尋的陣列。</span><span class="sxs-lookup"><span data-stu-id="c5d33-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="c5d33-112">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5d33-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5d33-113">最小的索引 `idx` （例如 `predicate(arr[idx])` true），如果沒有這類元素，則為-1。</span><span class="sxs-lookup"><span data-stu-id="c5d33-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c5d33-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="c5d33-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c5d33-115">不要</span><span class="sxs-lookup"><span data-stu-id="c5d33-115">'T</span></span>



## <a name="example"></a><span data-ttu-id="c5d33-116">範例</span><span class="sxs-lookup"><span data-stu-id="c5d33-116">Example</span></span>

<span data-ttu-id="c5d33-117">假設這 `IsEven : Int -> Bool` 是一個函式， `true` 只有在其輸入為偶數時才會傳回。</span><span class="sxs-lookup"><span data-stu-id="c5d33-117">Suppose that `IsEven : Int -> Bool` is a function that returns `true` if and only if its input is even.</span></span> <span data-ttu-id="c5d33-118">然後，您可以搭配使用， `IndexOf` 以找出陣列中的第一個偶數元素：</span><span class="sxs-lookup"><span data-stu-id="c5d33-118">Then, this can be used with `IndexOf` to find the first even element in an array:</span></span>

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```