---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 535f815503e20b5cee35f3f273a714203a4baf12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217776"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="5ab82-102">ApplyToEachC 操作</span><span class="sxs-lookup"><span data-stu-id="5ab82-102">ApplyToEachC operation</span></span>

<span data-ttu-id="5ab82-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5ab82-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5ab82-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5ab82-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5ab82-105">對暫存器中的每個元素套用單一量子位作業。</span><span class="sxs-lookup"><span data-stu-id="5ab82-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="5ab82-106">修飾詞 `C` 表示單一量子位作業是可控制的。</span><span class="sxs-lookup"><span data-stu-id="5ab82-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="5ab82-107">輸入</span><span class="sxs-lookup"><span data-stu-id="5ab82-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="5ab82-108">singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="5ab82-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="5ab82-109">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="5ab82-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="5ab82-110">register： t []</span><span class="sxs-lookup"><span data-stu-id="5ab82-110">register : 'T[]</span></span>

<span data-ttu-id="5ab82-111">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="5ab82-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ab82-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ab82-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5ab82-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="5ab82-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5ab82-114">不要</span><span class="sxs-lookup"><span data-stu-id="5ab82-114">'T</span></span>

<span data-ttu-id="5ab82-115">作業運作的目標。</span><span class="sxs-lookup"><span data-stu-id="5ab82-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ab82-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5ab82-116">See Also</span></span>

- [<span data-ttu-id="5ab82-117">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="5ab82-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)