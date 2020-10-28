---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: ApplyToEachIndexCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699212"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="0ebe7-102">ApplyToEachIndexCA 操作</span><span class="sxs-lookup"><span data-stu-id="0ebe7-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="0ebe7-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0ebe7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0ebe7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0ebe7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0ebe7-105">將單一量子位作業套用至暫存器中的每個索引元素。</span><span class="sxs-lookup"><span data-stu-id="0ebe7-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="0ebe7-106">修飾詞 `CA` 表示單一量子位作業是 adjointable 且可控制的。</span><span class="sxs-lookup"><span data-stu-id="0ebe7-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0ebe7-107">輸入</span><span class="sxs-lookup"><span data-stu-id="0ebe7-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj--ctl"></a><span data-ttu-id="0ebe7-108">singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0ebe7-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0ebe7-109">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="0ebe7-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="0ebe7-110">register： t []</span><span class="sxs-lookup"><span data-stu-id="0ebe7-110">register : 'T[]</span></span>

<span data-ttu-id="0ebe7-111">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="0ebe7-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0ebe7-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0ebe7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0ebe7-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="0ebe7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0ebe7-114">不要</span><span class="sxs-lookup"><span data-stu-id="0ebe7-114">'T</span></span>

<span data-ttu-id="0ebe7-115">每個作業作用所在的目標。</span><span class="sxs-lookup"><span data-stu-id="0ebe7-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ebe7-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0ebe7-116">See Also</span></span>

- [<span data-ttu-id="0ebe7-117">Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="0ebe7-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)