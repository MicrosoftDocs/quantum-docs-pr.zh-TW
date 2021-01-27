---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844608"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="bb9eb-102">ApplyToEachA 操作</span><span class="sxs-lookup"><span data-stu-id="bb9eb-102">ApplyToEachA operation</span></span>

<span data-ttu-id="bb9eb-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bb9eb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bb9eb-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bb9eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bb9eb-105">對暫存器中的每個元素套用單一量子位作業。</span><span class="sxs-lookup"><span data-stu-id="bb9eb-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="bb9eb-106">修飾詞 `A` 表示單一量子位作業為 adjointable。</span><span class="sxs-lookup"><span data-stu-id="bb9eb-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="bb9eb-107">輸入</span><span class="sxs-lookup"><span data-stu-id="bb9eb-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="bb9eb-108">singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="bb9eb-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="bb9eb-109">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="bb9eb-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="bb9eb-110">register： t []</span><span class="sxs-lookup"><span data-stu-id="bb9eb-110">register : 'T[]</span></span>

<span data-ttu-id="bb9eb-111">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="bb9eb-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bb9eb-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bb9eb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bb9eb-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="bb9eb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bb9eb-114">不要</span><span class="sxs-lookup"><span data-stu-id="bb9eb-114">'T</span></span>

<span data-ttu-id="bb9eb-115">作業運作的目標。</span><span class="sxs-lookup"><span data-stu-id="bb9eb-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="bb9eb-116">範例</span><span class="sxs-lookup"><span data-stu-id="bb9eb-116">Example</span></span>

<span data-ttu-id="bb9eb-117">準備三量子位 $ \ket{+} $ 狀態：</span><span class="sxs-lookup"><span data-stu-id="bb9eb-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="bb9eb-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bb9eb-118">See Also</span></span>

- [<span data-ttu-id="bb9eb-119">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="bb9eb-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)