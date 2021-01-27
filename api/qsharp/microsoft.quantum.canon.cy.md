---
uid: Microsoft.Quantum.Canon.CY
title: CY 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 862f058e630ee6d9159e0fe514ca2dd1179ea9a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840744"
---
# <a name="cy-operation"></a><span data-ttu-id="cba5f-102">CY 操作</span><span class="sxs-lookup"><span data-stu-id="cba5f-102">CY operation</span></span>

<span data-ttu-id="cba5f-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cba5f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cba5f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cba5f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cba5f-105">將受控制的 Y (CY) 閘道套用至一對量子位。</span><span class="sxs-lookup"><span data-stu-id="cba5f-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="cba5f-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i \\ \\ 0 & 0 & i & 0 \end{align}，$ $，其中資料列和資料行的組織方式如量子概念指南中所示。</span><span class="sxs-lookup"><span data-stu-id="cba5f-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cba5f-107">輸入</span><span class="sxs-lookup"><span data-stu-id="cba5f-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="cba5f-108">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cba5f-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cba5f-109">CY 閘道的控制量子位。</span><span class="sxs-lookup"><span data-stu-id="cba5f-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="cba5f-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cba5f-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cba5f-111">CY 閘道的目標量子位。</span><span class="sxs-lookup"><span data-stu-id="cba5f-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cba5f-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cba5f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cba5f-113">備註</span><span class="sxs-lookup"><span data-stu-id="cba5f-113">Remarks</span></span>

<span data-ttu-id="cba5f-114">相當於：</span><span class="sxs-lookup"><span data-stu-id="cba5f-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```