---
uid: Microsoft.Quantum.Canon.BoundA
title: BoundA 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3132bf198e98dd1a2b433f36b000060e7e721865
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216943"
---
# <a name="bounda-function"></a><span data-ttu-id="4adf2-102">BoundA 函式</span><span class="sxs-lookup"><span data-stu-id="4adf2-102">BoundA function</span></span>

<span data-ttu-id="4adf2-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4adf2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4adf2-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4adf2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4adf2-105">針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="4adf2-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="4adf2-106">修飾詞 `A` 表示陣列中的所有作業都是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="4adf2-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="4adf2-107">輸入</span><span class="sxs-lookup"><span data-stu-id="4adf2-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="4adf2-108">作業： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 []</span><span class="sxs-lookup"><span data-stu-id="4adf2-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="4adf2-109">要在指定的輸入上執行的一連串作業。</span><span class="sxs-lookup"><span data-stu-id="4adf2-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="4adf2-110">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="4adf2-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="4adf2-111">在其輸入上依序執行每個指定作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="4adf2-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4adf2-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="4adf2-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4adf2-113">不要</span><span class="sxs-lookup"><span data-stu-id="4adf2-113">'T</span></span>

<span data-ttu-id="4adf2-114">陣列中的每個作業所作用的目標。</span><span class="sxs-lookup"><span data-stu-id="4adf2-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="4adf2-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4adf2-115">See Also</span></span>

- [<span data-ttu-id="4adf2-116">Canon 系結</span><span class="sxs-lookup"><span data-stu-id="4adf2-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)