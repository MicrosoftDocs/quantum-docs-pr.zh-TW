---
uid: Microsoft.Quantum.Intrinsic.SWAP
title: 交換作業
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: SWAP
qsharp.summary: >-
  Applies the SWAP gate to a pair of qubits.

  \begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: e93c976f2fdf02de77fafa4d22e95fe9a33a9ba6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198413"
---
# <a name="swap-operation"></a><span data-ttu-id="060c1-102">交換作業</span><span class="sxs-lookup"><span data-stu-id="060c1-102">SWAP operation</span></span>

<span data-ttu-id="060c1-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="060c1-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="060c1-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="060c1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="060c1-105">將交換閘道套用至一對量子位。</span><span class="sxs-lookup"><span data-stu-id="060c1-105">Applies the SWAP gate to a pair of qubits.</span></span>

<span data-ttu-id="060c1-106">\begin{align} \operatorname{SWAP} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}，\end{align}</span><span class="sxs-lookup"><span data-stu-id="060c1-106">\begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="060c1-107">其中的資料列和資料行會依照量子概念指南中的順序排序。</span><span class="sxs-lookup"><span data-stu-id="060c1-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation SWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="060c1-108">輸入</span><span class="sxs-lookup"><span data-stu-id="060c1-108">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="060c1-109">qubit1： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="060c1-109">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="060c1-110">要交換的第一個量子位。</span><span class="sxs-lookup"><span data-stu-id="060c1-110">First qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="060c1-111">qubit2： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="060c1-111">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="060c1-112">要交換的第二個量子位。</span><span class="sxs-lookup"><span data-stu-id="060c1-112">Second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="060c1-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="060c1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="060c1-114">備註</span><span class="sxs-lookup"><span data-stu-id="060c1-114">Remarks</span></span>

<span data-ttu-id="060c1-115">相當於：</span><span class="sxs-lookup"><span data-stu-id="060c1-115">Equivalent to:</span></span>

```qsharp
CNOT(qubit1, qubit2);
CNOT(qubit2, qubit1);
CNOT(qubit1, qubit2);
```