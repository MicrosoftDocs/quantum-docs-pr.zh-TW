---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699091"
---
# <a name="boundc-function"></a><span data-ttu-id="34663-102">BoundC 函式</span><span class="sxs-lookup"><span data-stu-id="34663-102">BoundC function</span></span>

<span data-ttu-id="34663-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="34663-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="34663-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="34663-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="34663-105">針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="34663-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="34663-106">修飾詞 `C` 表示陣列中的所有作業都是可控制的。</span><span class="sxs-lookup"><span data-stu-id="34663-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="34663-107">輸入</span><span class="sxs-lookup"><span data-stu-id="34663-107">Input</span></span>

### <a name="operations--t--unit-ctl"></a><span data-ttu-id="34663-108">作業： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl []</span><span class="sxs-lookup"><span data-stu-id="34663-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="34663-109">要在指定的輸入上執行的一連串作業。</span><span class="sxs-lookup"><span data-stu-id="34663-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="34663-110">Output： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="34663-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="34663-111">在其輸入上依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="34663-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="34663-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="34663-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="34663-113">不要</span><span class="sxs-lookup"><span data-stu-id="34663-113">'T</span></span>

<span data-ttu-id="34663-114">陣列中的每個作業所作用的目標。</span><span class="sxs-lookup"><span data-stu-id="34663-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="34663-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="34663-115">See Also</span></span>

- [<span data-ttu-id="34663-116">Canon 系結</span><span class="sxs-lookup"><span data-stu-id="34663-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)