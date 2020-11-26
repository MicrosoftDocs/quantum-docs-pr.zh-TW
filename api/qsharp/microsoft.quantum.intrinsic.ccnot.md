---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: 715796ddd915d80036933e3f1ceefa97aa62cecf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212472"
---
# <a name="ccnot-operation"></a><span data-ttu-id="d0703-102">CCNOT 操作</span><span class="sxs-lookup"><span data-stu-id="d0703-102">CCNOT operation</span></span>

<span data-ttu-id="d0703-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d0703-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d0703-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d0703-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d0703-105">將雙向控制–不 (CCNOT) 閘道套用至三個量子位。</span><span class="sxs-lookup"><span data-stu-id="d0703-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d0703-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d0703-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="d0703-107">control1： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d0703-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d0703-108">CCNOT 閘道的第一個控制量子位。</span><span class="sxs-lookup"><span data-stu-id="d0703-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="d0703-109">control2： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d0703-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d0703-110">CCNOT 閘道的第二個控制項量子位。</span><span class="sxs-lookup"><span data-stu-id="d0703-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d0703-111">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d0703-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d0703-112">CCNOT 閘道的目標量子位。</span><span class="sxs-lookup"><span data-stu-id="d0703-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0703-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0703-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d0703-114">備註</span><span class="sxs-lookup"><span data-stu-id="d0703-114">Remarks</span></span>

<span data-ttu-id="d0703-115">相當於：</span><span class="sxs-lookup"><span data-stu-id="d0703-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```