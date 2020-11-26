---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 774a6f57566dce75b98290a7e81540b28afea1af
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216875"
---
# <a name="boundca-function"></a><span data-ttu-id="a7a8c-102">BoundCA 函式</span><span class="sxs-lookup"><span data-stu-id="a7a8c-102">BoundCA function</span></span>

<span data-ttu-id="a7a8c-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a7a8c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a7a8c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7a8c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7a8c-105">針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="a7a8c-106">修飾詞 `CA` 指出陣列中的所有作業都是 adjointable 且可控制的。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="a7a8c-107">輸入</span><span class="sxs-lookup"><span data-stu-id="a7a8c-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="a7a8c-108">作業： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="a7a8c-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="a7a8c-109">要在指定的輸入上執行的一連串作業。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="a7a8c-110">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a7a8c-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a7a8c-111">在其輸入上依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a7a8c-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="a7a8c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a7a8c-113">不要</span><span class="sxs-lookup"><span data-stu-id="a7a8c-113">'T</span></span>

<span data-ttu-id="a7a8c-114">陣列中的每個作業所作用的目標。</span><span class="sxs-lookup"><span data-stu-id="a7a8c-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7a8c-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a7a8c-115">See Also</span></span>

- [<span data-ttu-id="a7a8c-116">Canon 系結</span><span class="sxs-lookup"><span data-stu-id="a7a8c-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)