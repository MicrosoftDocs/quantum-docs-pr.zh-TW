---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217861"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="af4d4-102">ApplyToEach 操作</span><span class="sxs-lookup"><span data-stu-id="af4d4-102">ApplyToEach operation</span></span>

<span data-ttu-id="af4d4-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="af4d4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="af4d4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="af4d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="af4d4-105">對暫存器中的每個元素套用單一量子位作業。</span><span class="sxs-lookup"><span data-stu-id="af4d4-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="af4d4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="af4d4-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="af4d4-107">singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="af4d4-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="af4d4-108">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="af4d4-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="af4d4-109">register： t []</span><span class="sxs-lookup"><span data-stu-id="af4d4-109">register : 'T[]</span></span>

<span data-ttu-id="af4d4-110">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="af4d4-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="af4d4-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="af4d4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="af4d4-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="af4d4-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="af4d4-113">不要</span><span class="sxs-lookup"><span data-stu-id="af4d4-113">'T</span></span>

<span data-ttu-id="af4d4-114">作業運作的目標。</span><span class="sxs-lookup"><span data-stu-id="af4d4-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="af4d4-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="af4d4-115">See Also</span></span>

- [<span data-ttu-id="af4d4-116">Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="af4d4-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="af4d4-117">Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="af4d4-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="af4d4-118">Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="af4d4-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)