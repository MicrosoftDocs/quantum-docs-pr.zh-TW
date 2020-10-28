---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: ApplyToFirstThreeQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 61330f9e9b1f6b9f3965c9240505814b295aaefe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699193"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="14521-102">ApplyToFirstThreeQubits 操作</span><span class="sxs-lookup"><span data-stu-id="14521-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="14521-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="14521-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="14521-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="14521-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="14521-105">將作業套用至註冊中的前三個量子位。</span><span class="sxs-lookup"><span data-stu-id="14521-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="14521-106">輸入</span><span class="sxs-lookup"><span data-stu-id="14521-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="14521-107">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14521-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="14521-108">要套用至前三個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="14521-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="14521-109">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="14521-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="14521-110">量子位陣列至套用作業的前三個量子位。</span><span class="sxs-lookup"><span data-stu-id="14521-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="14521-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14521-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="14521-112">備註</span><span class="sxs-lookup"><span data-stu-id="14521-112">Remarks</span></span>

<span data-ttu-id="14521-113">這相當於：</span><span class="sxs-lookup"><span data-stu-id="14521-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="14521-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="14521-114">See Also</span></span>

- [<span data-ttu-id="14521-115">Canon. ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="14521-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="14521-116">Canon. ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="14521-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="14521-117">Canon. ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="14521-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)