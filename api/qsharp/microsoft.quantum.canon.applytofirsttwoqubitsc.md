---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: ApplyToFirstTwoQubitsC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 97706ffcc8700a0055ff37bbbaccc6fb4f8854b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699179"
---
# <a name="applytofirsttwoqubitsc-operation"></a><span data-ttu-id="b9f98-102">ApplyToFirstTwoQubitsC 操作</span><span class="sxs-lookup"><span data-stu-id="b9f98-102">ApplyToFirstTwoQubitsC operation</span></span>

<span data-ttu-id="b9f98-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b9f98-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b9f98-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b9f98-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b9f98-105">將作業套用至註冊中的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="b9f98-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="b9f98-106">修飾詞 `C` 表示作業可控制。</span><span class="sxs-lookup"><span data-stu-id="b9f98-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b9f98-107">輸入</span><span class="sxs-lookup"><span data-stu-id="b9f98-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl"></a><span data-ttu-id="b9f98-108">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)，[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="b9f98-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b9f98-109">要套用至前兩個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="b9f98-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="b9f98-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b9f98-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b9f98-111">量子位陣列至套用作業的前兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="b9f98-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b9f98-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b9f98-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b9f98-113">備註</span><span class="sxs-lookup"><span data-stu-id="b9f98-113">Remarks</span></span>

<span data-ttu-id="b9f98-114">這相當於：</span><span class="sxs-lookup"><span data-stu-id="b9f98-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="b9f98-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b9f98-115">See Also</span></span>

- [<span data-ttu-id="b9f98-116">Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="b9f98-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)