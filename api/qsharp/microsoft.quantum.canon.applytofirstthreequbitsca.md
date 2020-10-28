---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: ApplyToFirstThreeQubitsCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bd7a3ac260d370aae9da8691fcd34a8b6221d451
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699188"
---
# <a name="applytofirstthreequbitsca-operation"></a><span data-ttu-id="5756f-102">ApplyToFirstThreeQubitsCA 操作</span><span class="sxs-lookup"><span data-stu-id="5756f-102">ApplyToFirstThreeQubitsCA operation</span></span>

<span data-ttu-id="5756f-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5756f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5756f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5756f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5756f-105">將作業套用至註冊中的前三個量子位。</span><span class="sxs-lookup"><span data-stu-id="5756f-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="5756f-106">修飾詞 `CA` 表示作業可控制且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="5756f-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5756f-107">輸入</span><span class="sxs-lookup"><span data-stu-id="5756f-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-adj--ctl"></a><span data-ttu-id="5756f-108">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="5756f-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5756f-109">要套用至前三個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="5756f-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="5756f-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5756f-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5756f-111">量子位陣列至套用作業的前三個量子位。</span><span class="sxs-lookup"><span data-stu-id="5756f-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5756f-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5756f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5756f-113">備註</span><span class="sxs-lookup"><span data-stu-id="5756f-113">Remarks</span></span>

<span data-ttu-id="5756f-114">這相當於：</span><span class="sxs-lookup"><span data-stu-id="5756f-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="5756f-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5756f-115">See Also</span></span>

- [<span data-ttu-id="5756f-116">Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="5756f-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)