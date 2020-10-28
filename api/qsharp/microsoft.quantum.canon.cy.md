---
uid: Microsoft.Quantum.Canon.CY
title: CY 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 291891457ff39cf7092d17aa1d900dd0d35d9cf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699047"
---
# <a name="cy-operation"></a><span data-ttu-id="54bb5-102">CY 操作</span><span class="sxs-lookup"><span data-stu-id="54bb5-102">CY operation</span></span>

<span data-ttu-id="54bb5-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="54bb5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="54bb5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54bb5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54bb5-105">將受控制的 Y (CY) 閘道套用至一對量子位。</span><span class="sxs-lookup"><span data-stu-id="54bb5-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="54bb5-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i \\ \\ 0 & 0 & i & 0 \end{align}，$ $，其中資料列和資料行的組織方式如量子概念指南中所示。</span><span class="sxs-lookup"><span data-stu-id="54bb5-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="54bb5-107">輸入</span><span class="sxs-lookup"><span data-stu-id="54bb5-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="54bb5-108">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="54bb5-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="54bb5-109">CY 閘道的控制量子位。</span><span class="sxs-lookup"><span data-stu-id="54bb5-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="54bb5-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="54bb5-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="54bb5-111">CY 閘道的目標量子位。</span><span class="sxs-lookup"><span data-stu-id="54bb5-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54bb5-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54bb5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="54bb5-113">備註</span><span class="sxs-lookup"><span data-stu-id="54bb5-113">Remarks</span></span>

<span data-ttu-id="54bb5-114">相當於：</span><span class="sxs-lookup"><span data-stu-id="54bb5-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```