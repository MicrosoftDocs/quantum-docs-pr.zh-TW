---
uid: Microsoft.Quantum.Canon.Bound
title: 綁定函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841058"
---
# <a name="bound-function"></a><span data-ttu-id="d3f7c-102">綁定函數</span><span class="sxs-lookup"><span data-stu-id="d3f7c-102">Bound function</span></span>

<span data-ttu-id="d3f7c-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d3f7c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d3f7c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3f7c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3f7c-105">針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="d3f7c-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="d3f7c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d3f7c-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="d3f7c-107">作業： t => [單位](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="d3f7c-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="d3f7c-108">要在指定的輸入上執行的一連串作業。</span><span class="sxs-lookup"><span data-stu-id="d3f7c-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="d3f7c-109">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3f7c-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d3f7c-110">在其輸入上依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="d3f7c-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d3f7c-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="d3f7c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d3f7c-112">不要</span><span class="sxs-lookup"><span data-stu-id="d3f7c-112">'T</span></span>

<span data-ttu-id="d3f7c-113">陣列中的每個作業所作用的目標。</span><span class="sxs-lookup"><span data-stu-id="d3f7c-113">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="d3f7c-114">範例</span><span class="sxs-lookup"><span data-stu-id="d3f7c-114">Example</span></span>

<span data-ttu-id="d3f7c-115">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="d3f7c-115">The following are equivalent:</span></span>

```qsharp
let bound = Bound([U, V]);
bound(x);
```

<span data-ttu-id="d3f7c-116">及</span><span class="sxs-lookup"><span data-stu-id="d3f7c-116">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="d3f7c-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d3f7c-117">See Also</span></span>

- [<span data-ttu-id="d3f7c-118">Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="d3f7c-118">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="d3f7c-119">Canon. BoundA</span><span class="sxs-lookup"><span data-stu-id="d3f7c-119">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="d3f7c-120">Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="d3f7c-120">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)