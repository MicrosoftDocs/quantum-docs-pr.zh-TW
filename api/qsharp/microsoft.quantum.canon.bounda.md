---
uid: Microsoft.Quantum.Canon.BoundA
title: BoundA 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844549"
---
# <a name="bounda-function"></a><span data-ttu-id="fa875-102">BoundA 函式</span><span class="sxs-lookup"><span data-stu-id="fa875-102">BoundA function</span></span>

<span data-ttu-id="fa875-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fa875-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fa875-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa875-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa875-105">針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="fa875-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="fa875-106">修飾詞 `A` 表示陣列中的所有作業都是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="fa875-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="fa875-107">輸入</span><span class="sxs-lookup"><span data-stu-id="fa875-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="fa875-108">作業： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 []</span><span class="sxs-lookup"><span data-stu-id="fa875-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="fa875-109">要在指定的輸入上執行的一連串作業。</span><span class="sxs-lookup"><span data-stu-id="fa875-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="fa875-110">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="fa875-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="fa875-111">在其輸入上依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="fa875-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fa875-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="fa875-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fa875-113">不要</span><span class="sxs-lookup"><span data-stu-id="fa875-113">'T</span></span>

<span data-ttu-id="fa875-114">陣列中的每個作業所作用的目標。</span><span class="sxs-lookup"><span data-stu-id="fa875-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="fa875-115">範例</span><span class="sxs-lookup"><span data-stu-id="fa875-115">Example</span></span>

<span data-ttu-id="fa875-116">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="fa875-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

<span data-ttu-id="fa875-117">及</span><span class="sxs-lookup"><span data-stu-id="fa875-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="fa875-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fa875-118">See Also</span></span>

- [<span data-ttu-id="fa875-119">Canon 系結</span><span class="sxs-lookup"><span data-stu-id="fa875-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)