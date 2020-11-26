---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: ApplyToEachIndexCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: abb616498a8ff9c3348df81cf0ca1a1669561eec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208936"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="e4ea0-102">ApplyToEachIndexCA 操作</span><span class="sxs-lookup"><span data-stu-id="e4ea0-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="e4ea0-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e4ea0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e4ea0-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e4ea0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e4ea0-105">將單一量子位作業套用至暫存器中的每個索引元素。</span><span class="sxs-lookup"><span data-stu-id="e4ea0-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="e4ea0-106">修飾詞 `CA` 表示單一量子位作業是 adjointable 且可控制的。</span><span class="sxs-lookup"><span data-stu-id="e4ea0-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e4ea0-107">輸入</span><span class="sxs-lookup"><span data-stu-id="e4ea0-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="e4ea0-108">singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="e4ea0-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e4ea0-109">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="e4ea0-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="e4ea0-110">register： t []</span><span class="sxs-lookup"><span data-stu-id="e4ea0-110">register : 'T[]</span></span>

<span data-ttu-id="e4ea0-111">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="e4ea0-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e4ea0-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4ea0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e4ea0-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="e4ea0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e4ea0-114">不要</span><span class="sxs-lookup"><span data-stu-id="e4ea0-114">'T</span></span>

<span data-ttu-id="e4ea0-115">每個作業作用所在的目標。</span><span class="sxs-lookup"><span data-stu-id="e4ea0-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4ea0-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e4ea0-116">See Also</span></span>

- [<span data-ttu-id="e4ea0-117">Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="e4ea0-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)