---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9819e78760caf6180edc5c2ca5e402060e3029a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217793"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="48321-102">ApplyToEachA 操作</span><span class="sxs-lookup"><span data-stu-id="48321-102">ApplyToEachA operation</span></span>

<span data-ttu-id="48321-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="48321-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="48321-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48321-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48321-105">對暫存器中的每個元素套用單一量子位作業。</span><span class="sxs-lookup"><span data-stu-id="48321-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="48321-106">修飾詞 `A` 表示單一量子位作業為 adjointable。</span><span class="sxs-lookup"><span data-stu-id="48321-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="48321-107">輸入</span><span class="sxs-lookup"><span data-stu-id="48321-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="48321-108">singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="48321-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="48321-109">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="48321-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="48321-110">register： t []</span><span class="sxs-lookup"><span data-stu-id="48321-110">register : 'T[]</span></span>

<span data-ttu-id="48321-111">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="48321-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="48321-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48321-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="48321-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="48321-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48321-114">不要</span><span class="sxs-lookup"><span data-stu-id="48321-114">'T</span></span>

<span data-ttu-id="48321-115">作業運作的目標。</span><span class="sxs-lookup"><span data-stu-id="48321-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="48321-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="48321-116">See Also</span></span>

- [<span data-ttu-id="48321-117">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="48321-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)