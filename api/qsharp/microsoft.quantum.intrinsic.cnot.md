---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNOT 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700338"
---
# <a name="cnot-operation"></a><span data-ttu-id="39d55-102">CNOT 操作</span><span class="sxs-lookup"><span data-stu-id="39d55-102">CNOT operation</span></span>

<span data-ttu-id="39d55-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="39d55-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="39d55-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39d55-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39d55-105">將受控制-不 (CNOT) 閘道套用至一對量子位。</span><span class="sxs-lookup"><span data-stu-id="39d55-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="39d55-106">\begin{align} \operatorname{CNOT} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}，\end{align}</span><span class="sxs-lookup"><span data-stu-id="39d55-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="39d55-107">其中的資料列和資料行會依照量子概念指南中的順序排序。</span><span class="sxs-lookup"><span data-stu-id="39d55-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="39d55-108">輸入</span><span class="sxs-lookup"><span data-stu-id="39d55-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="39d55-109">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="39d55-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="39d55-110">CNOT 閘道的控制項量子位。</span><span class="sxs-lookup"><span data-stu-id="39d55-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="39d55-111">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="39d55-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="39d55-112">CNOT 閘道的目標量子位。</span><span class="sxs-lookup"><span data-stu-id="39d55-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39d55-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39d55-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="39d55-114">備註</span><span class="sxs-lookup"><span data-stu-id="39d55-114">Remarks</span></span>

<span data-ttu-id="39d55-115">相當於：</span><span class="sxs-lookup"><span data-stu-id="39d55-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```