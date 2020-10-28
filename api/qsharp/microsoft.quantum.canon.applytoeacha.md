---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9485c6549ed4e1a6fb3abdfa3f85ba35579d8b0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699221"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="27daa-102">ApplyToEachA 操作</span><span class="sxs-lookup"><span data-stu-id="27daa-102">ApplyToEachA operation</span></span>

<span data-ttu-id="27daa-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="27daa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="27daa-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27daa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27daa-105">對暫存器中的每個元素套用單一量子位作業。</span><span class="sxs-lookup"><span data-stu-id="27daa-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="27daa-106">修飾詞 `A` 表示單一量子位作業為 adjointable。</span><span class="sxs-lookup"><span data-stu-id="27daa-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="27daa-107">輸入</span><span class="sxs-lookup"><span data-stu-id="27daa-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj"></a><span data-ttu-id="27daa-108">singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="27daa-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="27daa-109">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="27daa-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="27daa-110">register： t []</span><span class="sxs-lookup"><span data-stu-id="27daa-110">register : 'T[]</span></span>

<span data-ttu-id="27daa-111">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="27daa-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27daa-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27daa-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="27daa-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="27daa-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="27daa-114">不要</span><span class="sxs-lookup"><span data-stu-id="27daa-114">'T</span></span>

<span data-ttu-id="27daa-115">作業運作的目標。</span><span class="sxs-lookup"><span data-stu-id="27daa-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="27daa-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="27daa-116">See Also</span></span>

- [<span data-ttu-id="27daa-117">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="27daa-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)