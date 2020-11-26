---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: ApplyToFirstTwoQubits 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: e4f1eb396efb390c7470ea2aaf5c3b5be60b8c1b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217402"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="b298c-102">ApplyToFirstTwoQubits 操作</span><span class="sxs-lookup"><span data-stu-id="b298c-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="b298c-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b298c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b298c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b298c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b298c-105">將作業套用至註冊中的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="b298c-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b298c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b298c-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="b298c-107">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)，[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b298c-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b298c-108">要套用至前兩個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="b298c-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="b298c-109">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b298c-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b298c-110">量子位陣列至套用作業的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="b298c-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b298c-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b298c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b298c-112">備註</span><span class="sxs-lookup"><span data-stu-id="b298c-112">Remarks</span></span>

<span data-ttu-id="b298c-113">這相當於：</span><span class="sxs-lookup"><span data-stu-id="b298c-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="b298c-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b298c-114">See Also</span></span>

- [<span data-ttu-id="b298c-115">Canon. ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="b298c-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="b298c-116">Canon. ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="b298c-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="b298c-117">Canon. ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="b298c-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)