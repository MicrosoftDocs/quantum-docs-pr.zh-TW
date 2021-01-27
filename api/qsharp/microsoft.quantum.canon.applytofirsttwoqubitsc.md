---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: ApplyToFirstTwoQubitsC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: f71209a806b0d1d712a3c776eb45e62d1cd5d5f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841340"
---
# <a name="applytofirsttwoqubitsc-operation"></a><span data-ttu-id="e1157-102">ApplyToFirstTwoQubitsC 操作</span><span class="sxs-lookup"><span data-stu-id="e1157-102">ApplyToFirstTwoQubitsC operation</span></span>

<span data-ttu-id="e1157-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e1157-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e1157-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1157-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1157-105">將作業套用至註冊中的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="e1157-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="e1157-106">修飾詞 `C` 表示作業可控制。</span><span class="sxs-lookup"><span data-stu-id="e1157-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="e1157-107">輸入</span><span class="sxs-lookup"><span data-stu-id="e1157-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-ctl"></a><span data-ttu-id="e1157-108">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)，[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit)  為 Ctl</span><span class="sxs-lookup"><span data-stu-id="e1157-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e1157-109">要套用至前兩個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="e1157-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="e1157-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e1157-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e1157-111">量子位陣列至套用作業的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="e1157-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1157-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1157-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e1157-113">備註</span><span class="sxs-lookup"><span data-stu-id="e1157-113">Remarks</span></span>

<span data-ttu-id="e1157-114">這相當於：</span><span class="sxs-lookup"><span data-stu-id="e1157-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="e1157-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e1157-115">See Also</span></span>

- [<span data-ttu-id="e1157-116">Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="e1157-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)