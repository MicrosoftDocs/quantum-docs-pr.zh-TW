---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: ApplyToFirstThreeQubits 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: b01c1072306cfdebcb90827a14683a32312481fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850692"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="0d4ca-102">ApplyToFirstThreeQubits 操作</span><span class="sxs-lookup"><span data-stu-id="0d4ca-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="0d4ca-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0d4ca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0d4ca-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d4ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d4ca-105">將作業套用至註冊中的前三個量子位。</span><span class="sxs-lookup"><span data-stu-id="0d4ca-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0d4ca-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0d4ca-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="0d4ca-107">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d4ca-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0d4ca-108">要套用至前三個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="0d4ca-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="0d4ca-109">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0d4ca-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0d4ca-110">量子位陣列至套用作業的前三個量子位。</span><span class="sxs-lookup"><span data-stu-id="0d4ca-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0d4ca-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d4ca-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0d4ca-112">備註</span><span class="sxs-lookup"><span data-stu-id="0d4ca-112">Remarks</span></span>

<span data-ttu-id="0d4ca-113">這相當於：</span><span class="sxs-lookup"><span data-stu-id="0d4ca-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="0d4ca-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0d4ca-114">See Also</span></span>

- [<span data-ttu-id="0d4ca-115">Canon. ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="0d4ca-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="0d4ca-116">Canon. ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="0d4ca-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="0d4ca-117">Canon. ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="0d4ca-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)