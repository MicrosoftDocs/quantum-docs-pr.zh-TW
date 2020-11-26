---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: dcfd4619a77413e71044e6a7d5fc19a9f22bbf94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217742"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="99da1-102">ApplyToEachCA 操作</span><span class="sxs-lookup"><span data-stu-id="99da1-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="99da1-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="99da1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="99da1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99da1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99da1-105">對暫存器中的每個元素套用單一量子位作業。</span><span class="sxs-lookup"><span data-stu-id="99da1-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="99da1-106">修飾詞 `CA` 表示單一量子位作業是可控制且 adjointable 的。</span><span class="sxs-lookup"><span data-stu-id="99da1-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="99da1-107">輸入</span><span class="sxs-lookup"><span data-stu-id="99da1-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="99da1-108">singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="99da1-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="99da1-109">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="99da1-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="99da1-110">register： t []</span><span class="sxs-lookup"><span data-stu-id="99da1-110">register : 'T[]</span></span>

<span data-ttu-id="99da1-111">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="99da1-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="99da1-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99da1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="99da1-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="99da1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="99da1-114">不要</span><span class="sxs-lookup"><span data-stu-id="99da1-114">'T</span></span>

<span data-ttu-id="99da1-115">作業運作的目標。</span><span class="sxs-lookup"><span data-stu-id="99da1-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="99da1-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="99da1-116">See Also</span></span>

- [<span data-ttu-id="99da1-117">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="99da1-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)