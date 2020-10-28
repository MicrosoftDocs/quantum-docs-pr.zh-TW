---
uid: Microsoft.Quantum.Canon.CX
title: CX 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: c430525b71ad4ef0812d90a8ff20c41a5d5b8708
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699049"
---
# <a name="cx-operation"></a><span data-ttu-id="e2024-102">CX 操作</span><span class="sxs-lookup"><span data-stu-id="e2024-102">CX operation</span></span>

<span data-ttu-id="e2024-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e2024-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e2024-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e2024-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e2024-105">將受控制 X (CX) 閘道套用至一對量子位。</span><span class="sxs-lookup"><span data-stu-id="e2024-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="e2024-106">$ $ \begin{align} \left ( \begin{matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}，$ $，其中資料列和資料行的組織方式與量子概念指南中的組織方式相同。</span><span class="sxs-lookup"><span data-stu-id="e2024-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e2024-107">輸入</span><span class="sxs-lookup"><span data-stu-id="e2024-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="e2024-108">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e2024-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e2024-109">適用于 CX 閘道的控制量子位。</span><span class="sxs-lookup"><span data-stu-id="e2024-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e2024-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e2024-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e2024-111">CX 閘道的目標量子位。</span><span class="sxs-lookup"><span data-stu-id="e2024-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e2024-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e2024-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e2024-113">備註</span><span class="sxs-lookup"><span data-stu-id="e2024-113">Remarks</span></span>

<span data-ttu-id="e2024-114">相當於：</span><span class="sxs-lookup"><span data-stu-id="e2024-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="e2024-115">以及：</span><span class="sxs-lookup"><span data-stu-id="e2024-115">and to:</span></span>

```qsharp
CNOT(control, target);
```