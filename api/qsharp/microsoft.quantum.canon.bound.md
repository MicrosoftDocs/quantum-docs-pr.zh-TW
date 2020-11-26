---
uid: Microsoft.Quantum.Canon.Bound
title: 綁定函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: c12ce37054ddde1b98778888e90916c6e4725814
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207593"
---
# <a name="bound-function"></a><span data-ttu-id="1dc6e-102">綁定函數</span><span class="sxs-lookup"><span data-stu-id="1dc6e-102">Bound function</span></span>

<span data-ttu-id="1dc6e-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1dc6e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1dc6e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1dc6e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1dc6e-105">針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="1dc6e-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="1dc6e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1dc6e-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="1dc6e-107">作業： t => [單位](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="1dc6e-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="1dc6e-108">要在指定的輸入上執行的一連串作業。</span><span class="sxs-lookup"><span data-stu-id="1dc6e-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="1dc6e-109">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1dc6e-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1dc6e-110">在其輸入上依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="1dc6e-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1dc6e-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="1dc6e-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1dc6e-112">不要</span><span class="sxs-lookup"><span data-stu-id="1dc6e-112">'T</span></span>

<span data-ttu-id="1dc6e-113">陣列中的每個作業所作用的目標。</span><span class="sxs-lookup"><span data-stu-id="1dc6e-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dc6e-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1dc6e-114">See Also</span></span>

- [<span data-ttu-id="1dc6e-115">Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="1dc6e-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="1dc6e-116">Canon. BoundA</span><span class="sxs-lookup"><span data-stu-id="1dc6e-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="1dc6e-117">Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="1dc6e-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)