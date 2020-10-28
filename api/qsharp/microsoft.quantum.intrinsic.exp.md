---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Exp 運算
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: b923374a954f90aba2deaead79dd419fbf67fea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697738"
---
# <a name="exp-operation"></a><span data-ttu-id="e8400-102">Exp 運算</span><span class="sxs-lookup"><span data-stu-id="e8400-102">Exp operation</span></span>

<span data-ttu-id="e8400-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="e8400-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="e8400-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8400-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8400-105">套用多量子位 Pauli 運算子的指數。</span><span class="sxs-lookup"><span data-stu-id="e8400-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="e8400-106">\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}，\end{align} where $P _i $ 是 $i $ th 的元素 `paulis` ，而 where $N = $ `Length(paulis)` 。</span><span class="sxs-lookup"><span data-stu-id="e8400-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e8400-107">輸入</span><span class="sxs-lookup"><span data-stu-id="e8400-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="e8400-108">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="e8400-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="e8400-109">單一量子位 Pauli 值的陣列，表示每個量子位上的 tensor 產品因素。</span><span class="sxs-lookup"><span data-stu-id="e8400-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="e8400-110">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8400-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8400-111">指定的多量子位 Pauli 運算子（目標暫存器要旋轉的角度）的角度。</span><span class="sxs-lookup"><span data-stu-id="e8400-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e8400-112">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e8400-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e8400-113">註冊以將指定的旋轉套用至。</span><span class="sxs-lookup"><span data-stu-id="e8400-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8400-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8400-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

