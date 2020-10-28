---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA
title: ApplyToFirstThreeQubitsA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 502d876df0ed643c40ce6ee48eaf496a90b0f5dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699191"
---
# <a name="applytofirstthreequbitsa-operation"></a><span data-ttu-id="dcc6d-102">ApplyToFirstThreeQubitsA 操作</span><span class="sxs-lookup"><span data-stu-id="dcc6d-102">ApplyToFirstThreeQubitsA operation</span></span>

<span data-ttu-id="dcc6d-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dcc6d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dcc6d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dcc6d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dcc6d-105">將作業套用至註冊中的前三個量子位。</span><span class="sxs-lookup"><span data-stu-id="dcc6d-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="dcc6d-106">修飾詞 `A` 表示作業 adjointable。</span><span class="sxs-lookup"><span data-stu-id="dcc6d-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsA (op : ((Qubit, Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="dcc6d-107">輸入</span><span class="sxs-lookup"><span data-stu-id="dcc6d-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-adj"></a><span data-ttu-id="dcc6d-108">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="dcc6d-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="dcc6d-109">要套用至前三個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="dcc6d-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="dcc6d-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dcc6d-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dcc6d-111">量子位陣列至套用作業的前三個量子位。</span><span class="sxs-lookup"><span data-stu-id="dcc6d-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dcc6d-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dcc6d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dcc6d-113">備註</span><span class="sxs-lookup"><span data-stu-id="dcc6d-113">Remarks</span></span>

<span data-ttu-id="dcc6d-114">這相當於：</span><span class="sxs-lookup"><span data-stu-id="dcc6d-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="dcc6d-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dcc6d-115">See Also</span></span>

- [<span data-ttu-id="dcc6d-116">Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="dcc6d-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)