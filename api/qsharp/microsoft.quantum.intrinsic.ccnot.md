---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697742"
---
# <a name="ccnot-operation"></a><span data-ttu-id="eb827-102">CCNOT 操作</span><span class="sxs-lookup"><span data-stu-id="eb827-102">CCNOT operation</span></span>

<span data-ttu-id="eb827-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="eb827-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="eb827-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb827-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb827-105">將雙向控制–不 (CCNOT) 閘道套用至三個量子位。</span><span class="sxs-lookup"><span data-stu-id="eb827-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="eb827-106">輸入</span><span class="sxs-lookup"><span data-stu-id="eb827-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="eb827-107">control1： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eb827-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="eb827-108">CCNOT 閘道的第一個控制量子位。</span><span class="sxs-lookup"><span data-stu-id="eb827-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="eb827-109">control2： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eb827-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="eb827-110">CCNOT 閘道的第二個控制項量子位。</span><span class="sxs-lookup"><span data-stu-id="eb827-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="eb827-111">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eb827-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="eb827-112">CCNOT 閘道的目標量子位。</span><span class="sxs-lookup"><span data-stu-id="eb827-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb827-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb827-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="eb827-114">備註</span><span class="sxs-lookup"><span data-stu-id="eb827-114">Remarks</span></span>

<span data-ttu-id="eb827-115">相當於：</span><span class="sxs-lookup"><span data-stu-id="eb827-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```