---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699472"
---
# <a name="indexof-function"></a><span data-ttu-id="f5298-102">IndexOf 函式</span><span class="sxs-lookup"><span data-stu-id="f5298-102">IndexOf function</span></span>

<span data-ttu-id="f5298-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f5298-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f5298-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5298-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5298-105">傳回陣列中第一個符合指定之述詞的第一個元素索引。</span><span class="sxs-lookup"><span data-stu-id="f5298-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="f5298-106">如果沒有這類元素，則傳回-1。</span><span class="sxs-lookup"><span data-stu-id="f5298-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="f5298-107">輸入</span><span class="sxs-lookup"><span data-stu-id="f5298-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="f5298-108">述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f5298-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f5298-109">在陣列元素上作用的述詞函式。</span><span class="sxs-lookup"><span data-stu-id="f5298-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="f5298-110">arr： t []</span><span class="sxs-lookup"><span data-stu-id="f5298-110">arr : 'T[]</span></span>

<span data-ttu-id="f5298-111">要使用指定述詞搜尋的陣列。</span><span class="sxs-lookup"><span data-stu-id="f5298-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="f5298-112">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f5298-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f5298-113">最小的索引 `idx` （例如 `predicate(arr[idx])` true），如果沒有這類元素，則為-1。</span><span class="sxs-lookup"><span data-stu-id="f5298-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f5298-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="f5298-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f5298-115">不要</span><span class="sxs-lookup"><span data-stu-id="f5298-115">'T</span></span>

