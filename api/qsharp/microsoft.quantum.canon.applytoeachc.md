---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699219"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="f6a93-102">ApplyToEachC 操作</span><span class="sxs-lookup"><span data-stu-id="f6a93-102">ApplyToEachC operation</span></span>

<span data-ttu-id="f6a93-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f6a93-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f6a93-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6a93-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6a93-105">對暫存器中的每個元素套用單一量子位作業。</span><span class="sxs-lookup"><span data-stu-id="f6a93-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="f6a93-106">修飾詞 `C` 表示單一量子位作業是可控制的。</span><span class="sxs-lookup"><span data-stu-id="f6a93-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f6a93-107">輸入</span><span class="sxs-lookup"><span data-stu-id="f6a93-107">Input</span></span>

### <a name="singleelementoperation--t--unit-ctl"></a><span data-ttu-id="f6a93-108">singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="f6a93-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f6a93-109">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="f6a93-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="f6a93-110">register： t []</span><span class="sxs-lookup"><span data-stu-id="f6a93-110">register : 'T[]</span></span>

<span data-ttu-id="f6a93-111">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="f6a93-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f6a93-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f6a93-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f6a93-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="f6a93-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f6a93-114">不要</span><span class="sxs-lookup"><span data-stu-id="f6a93-114">'T</span></span>

<span data-ttu-id="f6a93-115">作業運作的目標。</span><span class="sxs-lookup"><span data-stu-id="f6a93-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6a93-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f6a93-116">See Also</span></span>

- [<span data-ttu-id="f6a93-117">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="f6a93-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)