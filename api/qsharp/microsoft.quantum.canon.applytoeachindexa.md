---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: ApplyToEachIndexA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: e3ff812f14181e676fddf436af8a14f9a58271ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217589"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="21cf6-102">ApplyToEachIndexA 操作</span><span class="sxs-lookup"><span data-stu-id="21cf6-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="21cf6-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="21cf6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="21cf6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="21cf6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="21cf6-105">將單一量子位作業套用至暫存器中的每個索引元素。</span><span class="sxs-lookup"><span data-stu-id="21cf6-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="21cf6-106">修飾詞 `A` 表示單一量子位作業為 adjointable。</span><span class="sxs-lookup"><span data-stu-id="21cf6-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="21cf6-107">輸入</span><span class="sxs-lookup"><span data-stu-id="21cf6-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="21cf6-108">singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="21cf6-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="21cf6-109">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="21cf6-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="21cf6-110">register： t []</span><span class="sxs-lookup"><span data-stu-id="21cf6-110">register : 'T[]</span></span>

<span data-ttu-id="21cf6-111">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="21cf6-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="21cf6-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="21cf6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="21cf6-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="21cf6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="21cf6-114">不要</span><span class="sxs-lookup"><span data-stu-id="21cf6-114">'T</span></span>

<span data-ttu-id="21cf6-115">每個作業作用所在的目標。</span><span class="sxs-lookup"><span data-stu-id="21cf6-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="21cf6-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21cf6-116">See Also</span></span>

- [<span data-ttu-id="21cf6-117">Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="21cf6-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)