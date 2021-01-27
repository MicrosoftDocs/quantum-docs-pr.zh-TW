---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841035"
---
# <a name="boundc-function"></a><span data-ttu-id="7b9f2-102">BoundC 函式</span><span class="sxs-lookup"><span data-stu-id="7b9f2-102">BoundC function</span></span>

<span data-ttu-id="7b9f2-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7b9f2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7b9f2-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b9f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b9f2-105">針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="7b9f2-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="7b9f2-106">修飾詞 `C` 表示陣列中的所有作業都是可控制的。</span><span class="sxs-lookup"><span data-stu-id="7b9f2-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="7b9f2-107">輸入</span><span class="sxs-lookup"><span data-stu-id="7b9f2-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="7b9f2-108">作業： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl []</span><span class="sxs-lookup"><span data-stu-id="7b9f2-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="7b9f2-109">要在指定的輸入上執行的一連串作業。</span><span class="sxs-lookup"><span data-stu-id="7b9f2-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="7b9f2-110">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="7b9f2-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="7b9f2-111">在其輸入上依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="7b9f2-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7b9f2-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="7b9f2-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7b9f2-113">不要</span><span class="sxs-lookup"><span data-stu-id="7b9f2-113">'T</span></span>

<span data-ttu-id="7b9f2-114">陣列中的每個作業所作用的目標。</span><span class="sxs-lookup"><span data-stu-id="7b9f2-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="7b9f2-115">範例</span><span class="sxs-lookup"><span data-stu-id="7b9f2-115">Example</span></span>

<span data-ttu-id="7b9f2-116">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="7b9f2-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

<span data-ttu-id="7b9f2-117">及</span><span class="sxs-lookup"><span data-stu-id="7b9f2-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="7b9f2-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7b9f2-118">See Also</span></span>

- [<span data-ttu-id="7b9f2-119">Canon 系結</span><span class="sxs-lookup"><span data-stu-id="7b9f2-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)