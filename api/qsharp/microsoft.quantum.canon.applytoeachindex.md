---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 8b34dc24580a3df7ae2c13ef87a6fa10c7afd3f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844600"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="503d5-102">ApplyToEachIndex 操作</span><span class="sxs-lookup"><span data-stu-id="503d5-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="503d5-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="503d5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="503d5-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="503d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="503d5-105">將單一量子位作業套用至暫存器中的每個索引元素。</span><span class="sxs-lookup"><span data-stu-id="503d5-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="503d5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="503d5-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="503d5-107">singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="503d5-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="503d5-108">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="503d5-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="503d5-109">register： t []</span><span class="sxs-lookup"><span data-stu-id="503d5-109">register : 'T[]</span></span>

<span data-ttu-id="503d5-110">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="503d5-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="503d5-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="503d5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="503d5-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="503d5-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="503d5-113">不要</span><span class="sxs-lookup"><span data-stu-id="503d5-113">'T</span></span>

<span data-ttu-id="503d5-114">每個作業作用所在的目標。</span><span class="sxs-lookup"><span data-stu-id="503d5-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="503d5-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="503d5-115">See Also</span></span>

- [<span data-ttu-id="503d5-116">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="503d5-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="503d5-117">Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="503d5-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="503d5-118">Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="503d5-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="503d5-119">Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="503d5-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)