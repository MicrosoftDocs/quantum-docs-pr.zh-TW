---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697727"
---
# <a name="expfrac-operation"></a><span data-ttu-id="0c8c7-102">ExpFrac 操作</span><span class="sxs-lookup"><span data-stu-id="0c8c7-102">ExpFrac operation</span></span>

<span data-ttu-id="0c8c7-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="0c8c7-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="0c8c7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c8c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c8c7-105">以 dyadic 分數指定的引數，套用多量子位 Pauli 運算子的指數。</span><span class="sxs-lookup"><span data-stu-id="0c8c7-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="0c8c7-106">\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}，\end{align} where $P _i $ 是的 $i $ th 元素 `paulis` ，其中 $N = $ `Length(paulis)` 。</span><span class="sxs-lookup"><span data-stu-id="0c8c7-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0c8c7-107">輸入</span><span class="sxs-lookup"><span data-stu-id="0c8c7-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="0c8c7-108">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="0c8c7-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="0c8c7-109">單一量子位 Pauli 值的陣列，表示每個量子位上的 tensor 產品因素。</span><span class="sxs-lookup"><span data-stu-id="0c8c7-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="0c8c7-110">分子： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0c8c7-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0c8c7-111">分子 ($k $) 以 dyadic 分數表示量子位暫存器要旋轉的角度。</span><span class="sxs-lookup"><span data-stu-id="0c8c7-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="0c8c7-112">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0c8c7-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0c8c7-113">兩個 (的乘冪 $n $) 指定量子位註冊要旋轉的角度的分母。</span><span class="sxs-lookup"><span data-stu-id="0c8c7-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="0c8c7-114">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0c8c7-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0c8c7-115">註冊以將指定的旋轉套用至。</span><span class="sxs-lookup"><span data-stu-id="0c8c7-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c8c7-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c8c7-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

