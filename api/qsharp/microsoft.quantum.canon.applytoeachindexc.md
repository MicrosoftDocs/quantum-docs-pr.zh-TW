---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: ApplyToEachIndexC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: c005f616d580438891fbcb9f3c727b8e961e138d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850814"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="d033c-102">ApplyToEachIndexC 操作</span><span class="sxs-lookup"><span data-stu-id="d033c-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="d033c-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d033c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d033c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d033c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d033c-105">將單一量子位作業套用至暫存器中的每個索引元素。</span><span class="sxs-lookup"><span data-stu-id="d033c-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="d033c-106">修飾詞 `C` 表示單一量子位作業是可控制的。</span><span class="sxs-lookup"><span data-stu-id="d033c-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="d033c-107">輸入</span><span class="sxs-lookup"><span data-stu-id="d033c-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-ctl"></a><span data-ttu-id="d033c-108">singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="d033c-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d033c-109">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="d033c-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="d033c-110">register： t []</span><span class="sxs-lookup"><span data-stu-id="d033c-110">register : 'T[]</span></span>

<span data-ttu-id="d033c-111">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="d033c-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d033c-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d033c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d033c-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="d033c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d033c-114">不要</span><span class="sxs-lookup"><span data-stu-id="d033c-114">'T</span></span>

<span data-ttu-id="d033c-115">每個作業作用所在的目標。</span><span class="sxs-lookup"><span data-stu-id="d033c-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="d033c-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d033c-116">See Also</span></span>

- [<span data-ttu-id="d033c-117">Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="d033c-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)