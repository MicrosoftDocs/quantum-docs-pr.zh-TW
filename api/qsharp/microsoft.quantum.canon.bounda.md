---
uid: Microsoft.Quantum.Canon.BoundA
title: BoundA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699094"
---
# <a name="bounda-function"></a><span data-ttu-id="7df78-102">BoundA 函式</span><span class="sxs-lookup"><span data-stu-id="7df78-102">BoundA function</span></span>

<span data-ttu-id="7df78-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7df78-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7df78-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7df78-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7df78-105">針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="7df78-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="7df78-106">修飾詞 `A` 表示陣列中的所有作業都是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="7df78-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="7df78-107">輸入</span><span class="sxs-lookup"><span data-stu-id="7df78-107">Input</span></span>

### <a name="operations--t--unit-adj"></a><span data-ttu-id="7df78-108">作業： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 []</span><span class="sxs-lookup"><span data-stu-id="7df78-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="7df78-109">要在指定的輸入上執行的一連串作業。</span><span class="sxs-lookup"><span data-stu-id="7df78-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="7df78-110">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="7df78-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7df78-111">在其輸入上依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="7df78-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7df78-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="7df78-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7df78-113">不要</span><span class="sxs-lookup"><span data-stu-id="7df78-113">'T</span></span>

<span data-ttu-id="7df78-114">陣列中的每個作業所作用的目標。</span><span class="sxs-lookup"><span data-stu-id="7df78-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="7df78-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7df78-115">See Also</span></span>

- [<span data-ttu-id="7df78-116">Canon 系結</span><span class="sxs-lookup"><span data-stu-id="7df78-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)