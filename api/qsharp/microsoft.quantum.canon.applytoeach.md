---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699223"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="2c8ad-102">ApplyToEach 操作</span><span class="sxs-lookup"><span data-stu-id="2c8ad-102">ApplyToEach operation</span></span>

<span data-ttu-id="2c8ad-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2c8ad-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2c8ad-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c8ad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c8ad-105">對暫存器中的每個元素套用單一量子位作業。</span><span class="sxs-lookup"><span data-stu-id="2c8ad-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2c8ad-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2c8ad-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="2c8ad-107">singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c8ad-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2c8ad-108">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="2c8ad-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="2c8ad-109">register： t []</span><span class="sxs-lookup"><span data-stu-id="2c8ad-109">register : 'T[]</span></span>

<span data-ttu-id="2c8ad-110">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="2c8ad-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c8ad-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c8ad-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2c8ad-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="2c8ad-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2c8ad-113">不要</span><span class="sxs-lookup"><span data-stu-id="2c8ad-113">'T</span></span>

<span data-ttu-id="2c8ad-114">作業運作的目標。</span><span class="sxs-lookup"><span data-stu-id="2c8ad-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c8ad-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2c8ad-115">See Also</span></span>

- [<span data-ttu-id="2c8ad-116">Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="2c8ad-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="2c8ad-117">Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="2c8ad-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="2c8ad-118">Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="2c8ad-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)