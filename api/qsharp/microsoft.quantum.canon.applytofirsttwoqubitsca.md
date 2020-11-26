---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: ApplyToFirstTwoQubitsCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: a2281776b617d5c3f8cc706ea09d14995fce4a27
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208647"
---
# <a name="applytofirsttwoqubitsca-operation"></a><span data-ttu-id="d5bbc-102">ApplyToFirstTwoQubitsCA 操作</span><span class="sxs-lookup"><span data-stu-id="d5bbc-102">ApplyToFirstTwoQubitsCA operation</span></span>

<span data-ttu-id="d5bbc-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d5bbc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d5bbc-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d5bbc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d5bbc-105">將作業套用至註冊中的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="d5bbc-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="d5bbc-106">修飾詞 `CA` 表示作業可控制且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="d5bbc-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d5bbc-107">輸入</span><span class="sxs-lookup"><span data-stu-id="d5bbc-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="d5bbc-108">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)，[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d5bbc-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d5bbc-109">要套用至前兩個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="d5bbc-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="d5bbc-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d5bbc-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d5bbc-111">量子位陣列至套用作業的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="d5bbc-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5bbc-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5bbc-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d5bbc-113">備註</span><span class="sxs-lookup"><span data-stu-id="d5bbc-113">Remarks</span></span>

<span data-ttu-id="d5bbc-114">這相當於：</span><span class="sxs-lookup"><span data-stu-id="d5bbc-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="d5bbc-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d5bbc-115">See Also</span></span>

- [<span data-ttu-id="d5bbc-116">Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="d5bbc-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)