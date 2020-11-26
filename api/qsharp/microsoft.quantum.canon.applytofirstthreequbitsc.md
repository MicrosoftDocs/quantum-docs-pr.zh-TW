---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: ApplyToFirstThreeQubitsC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: cb6945f5aa398d0bf6417c5cfd21142008a54b13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217436"
---
# <a name="applytofirstthreequbitsc-operation"></a><span data-ttu-id="45c9b-102">ApplyToFirstThreeQubitsC 操作</span><span class="sxs-lookup"><span data-stu-id="45c9b-102">ApplyToFirstThreeQubitsC operation</span></span>

<span data-ttu-id="45c9b-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="45c9b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="45c9b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45c9b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45c9b-105">將作業套用至註冊中的前三個量子位。</span><span class="sxs-lookup"><span data-stu-id="45c9b-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="45c9b-106">修飾詞 `C` 表示作業可控制。</span><span class="sxs-lookup"><span data-stu-id="45c9b-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="45c9b-107">輸入</span><span class="sxs-lookup"><span data-stu-id="45c9b-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit--is-ctl"></a><span data-ttu-id="45c9b-108">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)，[量子位](xref:microsoft.quantum.lang-ref.qubit)，[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  為 Ctl</span><span class="sxs-lookup"><span data-stu-id="45c9b-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="45c9b-109">要套用至前三個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="45c9b-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="45c9b-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="45c9b-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="45c9b-111">量子位陣列至套用作業的前三個量子位。</span><span class="sxs-lookup"><span data-stu-id="45c9b-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45c9b-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45c9b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="45c9b-113">備註</span><span class="sxs-lookup"><span data-stu-id="45c9b-113">Remarks</span></span>

<span data-ttu-id="45c9b-114">這相當於：</span><span class="sxs-lookup"><span data-stu-id="45c9b-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="45c9b-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="45c9b-115">See Also</span></span>

- [<span data-ttu-id="45c9b-116">Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="45c9b-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)