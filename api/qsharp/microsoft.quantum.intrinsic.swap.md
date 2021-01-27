---
uid: Microsoft.Quantum.Intrinsic.SWAP
title: 交換作業
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: SWAP
qsharp.summary: >-
  Applies the SWAP gate to a pair of qubits.

  \begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 4d8d037404ac835a1dd032790e7fd03f29591c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849260"
---
# <a name="swap-operation"></a><span data-ttu-id="cbde2-102">交換作業</span><span class="sxs-lookup"><span data-stu-id="cbde2-102">SWAP operation</span></span>

<span data-ttu-id="cbde2-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cbde2-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cbde2-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cbde2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cbde2-105">將交換閘道套用至一對量子位。</span><span class="sxs-lookup"><span data-stu-id="cbde2-105">Applies the SWAP gate to a pair of qubits.</span></span>

<span data-ttu-id="cbde2-106">\begin{align} \operatorname{SWAP} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}，\end{align}</span><span class="sxs-lookup"><span data-stu-id="cbde2-106">\begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="cbde2-107">其中的資料列和資料行會依照量子概念指南中的順序排序。</span><span class="sxs-lookup"><span data-stu-id="cbde2-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation SWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cbde2-108">輸入</span><span class="sxs-lookup"><span data-stu-id="cbde2-108">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="cbde2-109">qubit1： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cbde2-109">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cbde2-110">要交換的第一個量子位。</span><span class="sxs-lookup"><span data-stu-id="cbde2-110">First qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="cbde2-111">qubit2： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cbde2-111">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cbde2-112">要交換的第二個量子位。</span><span class="sxs-lookup"><span data-stu-id="cbde2-112">Second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cbde2-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cbde2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cbde2-114">備註</span><span class="sxs-lookup"><span data-stu-id="cbde2-114">Remarks</span></span>

<span data-ttu-id="cbde2-115">相當於：</span><span class="sxs-lookup"><span data-stu-id="cbde2-115">Equivalent to:</span></span>

```qsharp
CNOT(qubit1, qubit2);
CNOT(qubit2, qubit1);
CNOT(qubit1, qubit2);
```