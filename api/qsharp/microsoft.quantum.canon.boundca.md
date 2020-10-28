---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699086"
---
# <a name="boundca-function"></a><span data-ttu-id="39407-102">BoundCA 函式</span><span class="sxs-lookup"><span data-stu-id="39407-102">BoundCA function</span></span>

<span data-ttu-id="39407-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39407-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39407-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39407-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39407-105">針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="39407-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="39407-106">修飾詞 `CA` 指出陣列中的所有作業都是 adjointable 且可控制的。</span><span class="sxs-lookup"><span data-stu-id="39407-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="39407-107">輸入</span><span class="sxs-lookup"><span data-stu-id="39407-107">Input</span></span>

### <a name="operations--t--unit-adj--ctl"></a><span data-ttu-id="39407-108">作業： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="39407-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="39407-109">要在指定的輸入上執行的一連串作業。</span><span class="sxs-lookup"><span data-stu-id="39407-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="39407-110">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="39407-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="39407-111">在其輸入上依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="39407-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="39407-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="39407-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39407-113">不要</span><span class="sxs-lookup"><span data-stu-id="39407-113">'T</span></span>

<span data-ttu-id="39407-114">陣列中的每個作業所作用的目標。</span><span class="sxs-lookup"><span data-stu-id="39407-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="39407-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="39407-115">See Also</span></span>

- [<span data-ttu-id="39407-116">Canon 系結</span><span class="sxs-lookup"><span data-stu-id="39407-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)