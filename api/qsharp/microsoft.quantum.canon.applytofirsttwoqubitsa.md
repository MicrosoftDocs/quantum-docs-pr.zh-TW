---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: ApplyToFirstTwoQubitsA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 1a286c167a87372dc89d62ab3733b186298c43a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208698"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="3bb13-102">ApplyToFirstTwoQubitsA 操作</span><span class="sxs-lookup"><span data-stu-id="3bb13-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="3bb13-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3bb13-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3bb13-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3bb13-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3bb13-105">將作業套用至註冊中的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="3bb13-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="3bb13-106">修飾詞 `A` 表示作業 adjointable。</span><span class="sxs-lookup"><span data-stu-id="3bb13-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="3bb13-107">輸入</span><span class="sxs-lookup"><span data-stu-id="3bb13-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj"></a><span data-ttu-id="3bb13-108">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)，[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="3bb13-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3bb13-109">要套用至前兩個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="3bb13-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="3bb13-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3bb13-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3bb13-111">量子位陣列至套用作業的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="3bb13-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3bb13-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3bb13-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3bb13-113">備註</span><span class="sxs-lookup"><span data-stu-id="3bb13-113">Remarks</span></span>

<span data-ttu-id="3bb13-114">這相當於：</span><span class="sxs-lookup"><span data-stu-id="3bb13-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="3bb13-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3bb13-115">See Also</span></span>

- [<span data-ttu-id="3bb13-116">Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="3bb13-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)