---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: ApplyToFirstTwoQubitsA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 911e9bc3d02bf6c0395c30fa167a6cb730dc666e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699182"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="09c4c-102">ApplyToFirstTwoQubitsA 操作</span><span class="sxs-lookup"><span data-stu-id="09c4c-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="09c4c-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="09c4c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="09c4c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09c4c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="09c4c-105">將作業套用至註冊中的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="09c4c-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="09c4c-106">修飾詞 `A` 表示作業 adjointable。</span><span class="sxs-lookup"><span data-stu-id="09c4c-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="09c4c-107">輸入</span><span class="sxs-lookup"><span data-stu-id="09c4c-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj"></a><span data-ttu-id="09c4c-108">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)，[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="09c4c-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="09c4c-109">要套用至前兩個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="09c4c-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="09c4c-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="09c4c-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="09c4c-111">量子位陣列至套用作業的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="09c4c-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="09c4c-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09c4c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="09c4c-113">備註</span><span class="sxs-lookup"><span data-stu-id="09c4c-113">Remarks</span></span>

<span data-ttu-id="09c4c-114">這相當於：</span><span class="sxs-lookup"><span data-stu-id="09c4c-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="09c4c-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="09c4c-115">See Also</span></span>

- [<span data-ttu-id="09c4c-116">Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="09c4c-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)