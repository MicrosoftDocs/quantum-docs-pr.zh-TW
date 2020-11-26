---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: ApplyToFirstThreeQubits 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 5572bd2a096a4f9bdb1153ae80950ae854965b82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217452"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="56ff1-102">ApplyToFirstThreeQubits 操作</span><span class="sxs-lookup"><span data-stu-id="56ff1-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="56ff1-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="56ff1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="56ff1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56ff1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56ff1-105">將作業套用至註冊中的前三個量子位。</span><span class="sxs-lookup"><span data-stu-id="56ff1-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="56ff1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="56ff1-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="56ff1-107">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56ff1-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="56ff1-108">要套用至前三個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="56ff1-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="56ff1-109">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="56ff1-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="56ff1-110">量子位陣列至套用作業的前三個量子位。</span><span class="sxs-lookup"><span data-stu-id="56ff1-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="56ff1-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56ff1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="56ff1-112">備註</span><span class="sxs-lookup"><span data-stu-id="56ff1-112">Remarks</span></span>

<span data-ttu-id="56ff1-113">這相當於：</span><span class="sxs-lookup"><span data-stu-id="56ff1-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="56ff1-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="56ff1-114">See Also</span></span>

- [<span data-ttu-id="56ff1-115">Canon. ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="56ff1-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="56ff1-116">Canon. ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="56ff1-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="56ff1-117">Canon. ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="56ff1-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)