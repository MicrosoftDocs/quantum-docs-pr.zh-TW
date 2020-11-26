---
uid: Microsoft.Quantum.Canon.CZ
title: CZ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 419082dbf8f96a9fe2dfabeab77e1823cb59a8f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207202"
---
# <a name="cz-operation"></a><span data-ttu-id="dd022-102">CZ 操作</span><span class="sxs-lookup"><span data-stu-id="dd022-102">CZ operation</span></span>

<span data-ttu-id="dd022-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dd022-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dd022-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd022-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd022-105">將控制的 Z (CZ) 閘道套用至一對量子位。</span><span class="sxs-lookup"><span data-stu-id="dd022-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="dd022-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}，$ $，其中資料列和資料行的組織方式如量子概念指南中所示。</span><span class="sxs-lookup"><span data-stu-id="dd022-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dd022-107">輸入</span><span class="sxs-lookup"><span data-stu-id="dd022-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="dd022-108">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dd022-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dd022-109">CZ 閘道的控制項量子位。</span><span class="sxs-lookup"><span data-stu-id="dd022-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="dd022-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dd022-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dd022-111">CZ 閘道的目標量子位。</span><span class="sxs-lookup"><span data-stu-id="dd022-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd022-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd022-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dd022-113">備註</span><span class="sxs-lookup"><span data-stu-id="dd022-113">Remarks</span></span>

<span data-ttu-id="dd022-114">相當於：</span><span class="sxs-lookup"><span data-stu-id="dd022-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```