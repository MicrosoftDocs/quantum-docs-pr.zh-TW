---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699216"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="86cca-102">ApplyToEachIndex 操作</span><span class="sxs-lookup"><span data-stu-id="86cca-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="86cca-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="86cca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="86cca-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="86cca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="86cca-105">將單一量子位作業套用至暫存器中的每個索引元素。</span><span class="sxs-lookup"><span data-stu-id="86cca-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="86cca-106">輸入</span><span class="sxs-lookup"><span data-stu-id="86cca-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="86cca-107">singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="86cca-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="86cca-108">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="86cca-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="86cca-109">register： t []</span><span class="sxs-lookup"><span data-stu-id="86cca-109">register : 'T[]</span></span>

<span data-ttu-id="86cca-110">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="86cca-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="86cca-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="86cca-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="86cca-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="86cca-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="86cca-113">不要</span><span class="sxs-lookup"><span data-stu-id="86cca-113">'T</span></span>

<span data-ttu-id="86cca-114">每個作業作用所在的目標。</span><span class="sxs-lookup"><span data-stu-id="86cca-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="86cca-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="86cca-115">See Also</span></span>

- [<span data-ttu-id="86cca-116">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="86cca-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="86cca-117">Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="86cca-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="86cca-118">Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="86cca-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="86cca-119">Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="86cca-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)