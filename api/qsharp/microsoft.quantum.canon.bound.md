---
uid: Microsoft.Quantum.Canon.Bound
title: 綁定函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699096"
---
# <a name="bound-function"></a><span data-ttu-id="afd0b-102">綁定函數</span><span class="sxs-lookup"><span data-stu-id="afd0b-102">Bound function</span></span>

<span data-ttu-id="afd0b-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="afd0b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="afd0b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afd0b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afd0b-105">針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="afd0b-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="afd0b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="afd0b-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="afd0b-107">作業： t => [單位](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="afd0b-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="afd0b-108">要在指定的輸入上執行的一連串作業。</span><span class="sxs-lookup"><span data-stu-id="afd0b-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="afd0b-109">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="afd0b-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="afd0b-110">在其輸入上依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="afd0b-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="afd0b-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="afd0b-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="afd0b-112">不要</span><span class="sxs-lookup"><span data-stu-id="afd0b-112">'T</span></span>

<span data-ttu-id="afd0b-113">陣列中的每個作業所作用的目標。</span><span class="sxs-lookup"><span data-stu-id="afd0b-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="afd0b-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="afd0b-114">See Also</span></span>

- [<span data-ttu-id="afd0b-115">Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="afd0b-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="afd0b-116">Canon. BoundA</span><span class="sxs-lookup"><span data-stu-id="afd0b-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="afd0b-117">Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="afd0b-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)