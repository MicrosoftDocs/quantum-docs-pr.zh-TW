---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: ApplyToFirstTwoQubits 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: c89ea89c055a950a9aee533653d40c84d8e179da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841372"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="58758-102">ApplyToFirstTwoQubits 操作</span><span class="sxs-lookup"><span data-stu-id="58758-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="58758-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="58758-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="58758-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="58758-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="58758-105">將作業套用至註冊中的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="58758-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="58758-106">輸入</span><span class="sxs-lookup"><span data-stu-id="58758-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="58758-107">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)，[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="58758-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="58758-108">要套用至前兩個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="58758-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="58758-109">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="58758-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="58758-110">量子位陣列至套用作業的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="58758-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="58758-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="58758-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="58758-112">備註</span><span class="sxs-lookup"><span data-stu-id="58758-112">Remarks</span></span>

<span data-ttu-id="58758-113">這相當於：</span><span class="sxs-lookup"><span data-stu-id="58758-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="58758-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="58758-114">See Also</span></span>

- [<span data-ttu-id="58758-115">Canon. ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="58758-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="58758-116">Canon. ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="58758-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="58758-117">Canon. ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="58758-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)