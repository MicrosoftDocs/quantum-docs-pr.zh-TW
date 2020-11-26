---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: cb72ca5b3dab99b9ee8a994ba9fde46e0eae5594
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207508"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="cc9ea-102">CControlledA 函式</span><span class="sxs-lookup"><span data-stu-id="cc9ea-102">CControlledA function</span></span>

<span data-ttu-id="cc9ea-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cc9ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cc9ea-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc9ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc9ea-105">在指定作業作業的情況下，會傳回新的作業，如果傳統的控制項位為 true，就會套用 op。</span><span class="sxs-lookup"><span data-stu-id="cc9ea-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="cc9ea-106">如果為，則不 `false` 會發生任何事。</span><span class="sxs-lookup"><span data-stu-id="cc9ea-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="cc9ea-107">修飾詞 `A` 表示作業 adjointable。</span><span class="sxs-lookup"><span data-stu-id="cc9ea-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="cc9ea-108">輸入</span><span class="sxs-lookup"><span data-stu-id="cc9ea-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="cc9ea-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="cc9ea-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="cc9ea-110">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="cc9ea-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj"></a><span data-ttu-id="cc9ea-111">輸出： ([Bool](xref:microsoft.quantum.lang-ref.bool)，t) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="cc9ea-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="cc9ea-112">如果傳統控制位為 true，則為 op 的新作業。</span><span class="sxs-lookup"><span data-stu-id="cc9ea-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cc9ea-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="cc9ea-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cc9ea-114">不要</span><span class="sxs-lookup"><span data-stu-id="cc9ea-114">'T</span></span>

<span data-ttu-id="cc9ea-115">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="cc9ea-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc9ea-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cc9ea-116">See Also</span></span>

- [<span data-ttu-id="cc9ea-117">Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="cc9ea-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)