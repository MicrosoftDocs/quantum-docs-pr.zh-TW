---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 746bc19f7a137ef476a25abdabc4737ed6727ff2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217606"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="fc9a3-102">ApplyToEachIndex 操作</span><span class="sxs-lookup"><span data-stu-id="fc9a3-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="fc9a3-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fc9a3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fc9a3-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc9a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc9a3-105">將單一量子位作業套用至暫存器中的每個索引元素。</span><span class="sxs-lookup"><span data-stu-id="fc9a3-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="fc9a3-106">輸入</span><span class="sxs-lookup"><span data-stu-id="fc9a3-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="fc9a3-107">singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc9a3-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fc9a3-108">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="fc9a3-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="fc9a3-109">register： t []</span><span class="sxs-lookup"><span data-stu-id="fc9a3-109">register : 'T[]</span></span>

<span data-ttu-id="fc9a3-110">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="fc9a3-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc9a3-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc9a3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fc9a3-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="fc9a3-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fc9a3-113">不要</span><span class="sxs-lookup"><span data-stu-id="fc9a3-113">'T</span></span>

<span data-ttu-id="fc9a3-114">每個作業作用所在的目標。</span><span class="sxs-lookup"><span data-stu-id="fc9a3-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc9a3-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fc9a3-115">See Also</span></span>

- [<span data-ttu-id="fc9a3-116">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="fc9a3-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="fc9a3-117">Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="fc9a3-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="fc9a3-118">Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="fc9a3-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="fc9a3-119">Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="fc9a3-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)