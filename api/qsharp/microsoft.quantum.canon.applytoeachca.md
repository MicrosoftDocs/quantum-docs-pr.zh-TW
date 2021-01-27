---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: c85b33760eba8d10d9650be2f8306e4afdd1f307
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841481"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="c8245-102">ApplyToEachCA 操作</span><span class="sxs-lookup"><span data-stu-id="c8245-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="c8245-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c8245-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c8245-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8245-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8245-105">對暫存器中的每個元素套用單一量子位作業。</span><span class="sxs-lookup"><span data-stu-id="c8245-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="c8245-106">修飾詞 `CA` 表示單一量子位作業是可控制且 adjointable 的。</span><span class="sxs-lookup"><span data-stu-id="c8245-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c8245-107">輸入</span><span class="sxs-lookup"><span data-stu-id="c8245-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="c8245-108">singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c8245-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c8245-109">要套用至每個量子位的作業。</span><span class="sxs-lookup"><span data-stu-id="c8245-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="c8245-110">register： t []</span><span class="sxs-lookup"><span data-stu-id="c8245-110">register : 'T[]</span></span>

<span data-ttu-id="c8245-111">要套用指定作業的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="c8245-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c8245-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8245-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c8245-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="c8245-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c8245-114">不要</span><span class="sxs-lookup"><span data-stu-id="c8245-114">'T</span></span>

<span data-ttu-id="c8245-115">作業運作的目標。</span><span class="sxs-lookup"><span data-stu-id="c8245-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="c8245-116">範例</span><span class="sxs-lookup"><span data-stu-id="c8245-116">Example</span></span>

<span data-ttu-id="c8245-117">準備三量子位 $ \ket{+} $ 狀態：</span><span class="sxs-lookup"><span data-stu-id="c8245-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="c8245-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c8245-118">See Also</span></span>

- [<span data-ttu-id="c8245-119">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="c8245-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)