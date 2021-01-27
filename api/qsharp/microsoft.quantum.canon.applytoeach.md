---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844631"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="72b18-102">ApplyToEach 操作</span><span class="sxs-lookup"><span data-stu-id="72b18-102">ApplyToEach operation</span></span>

<span data-ttu-id="72b18-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="72b18-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="72b18-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72b18-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72b18-105">對暫存器中的每個元素套用單一量子位作業。</span><span class="sxs-lookup"><span data-stu-id="72b18-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="72b18-106">輸入</span><span class="sxs-lookup"><span data-stu-id="72b18-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="72b18-107">singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72b18-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="72b18-108">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="72b18-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="72b18-109">register： t []</span><span class="sxs-lookup"><span data-stu-id="72b18-109">register : 'T[]</span></span>

<span data-ttu-id="72b18-110">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="72b18-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72b18-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72b18-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="72b18-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="72b18-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="72b18-113">不要</span><span class="sxs-lookup"><span data-stu-id="72b18-113">'T</span></span>

<span data-ttu-id="72b18-114">作業運作的目標。</span><span class="sxs-lookup"><span data-stu-id="72b18-114">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="72b18-115">範例</span><span class="sxs-lookup"><span data-stu-id="72b18-115">Example</span></span>

<span data-ttu-id="72b18-116">準備三量子位 $ \ket{+} $ 狀態：</span><span class="sxs-lookup"><span data-stu-id="72b18-116">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="72b18-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="72b18-117">See Also</span></span>

- [<span data-ttu-id="72b18-118">Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="72b18-118">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="72b18-119">Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="72b18-119">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="72b18-120">Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="72b18-120">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)