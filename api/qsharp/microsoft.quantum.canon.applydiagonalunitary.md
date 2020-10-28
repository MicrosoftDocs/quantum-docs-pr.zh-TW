---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: ApplyDiagonalUnitary 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 6ecacf6e4fe2c505036de208c8aeb5350e479e3c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699324"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="e40a6-102">ApplyDiagonalUnitary 操作</span><span class="sxs-lookup"><span data-stu-id="e40a6-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="e40a6-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e40a6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e40a6-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e40a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e40a6-105">將複雜階段的陣列套用至量子位註冊的數值基礎狀態。</span><span class="sxs-lookup"><span data-stu-id="e40a6-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="e40a6-106">描述</span><span class="sxs-lookup"><span data-stu-id="e40a6-106">Description</span></span>

<span data-ttu-id="e40a6-107">此作業會在 $n $ 量子位 number state $ \ket{j} $ 上，執行套用複雜階段 $e ^ {i \ theta_j} $ 的對角線。</span><span class="sxs-lookup"><span data-stu-id="e40a6-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="e40a6-108">尤其是，這項作業可以由單一</span><span class="sxs-lookup"><span data-stu-id="e40a6-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="e40a6-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}。</span><span class="sxs-lookup"><span data-stu-id="e40a6-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="e40a6-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="e40a6-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="e40a6-111">輸入</span><span class="sxs-lookup"><span data-stu-id="e40a6-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="e40a6-112">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e40a6-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e40a6-113">最多 $ 2 ^ n $ 係數 $ \ theta_j $ 的陣列。</span><span class="sxs-lookup"><span data-stu-id="e40a6-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="e40a6-114">$J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="e40a6-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="e40a6-115">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e40a6-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e40a6-116">以位元組由大到小的格式，$n $ 量子位 control register 編碼數位狀態 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="e40a6-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e40a6-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e40a6-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e40a6-118">備註</span><span class="sxs-lookup"><span data-stu-id="e40a6-118">Remarks</span></span>

<span data-ttu-id="e40a6-119">`coefficients` 如果指定了少於 $ 2 ^ n $ 的元素，則會以 $ \ theta_j = $0.0 填補。</span><span class="sxs-lookup"><span data-stu-id="e40a6-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="e40a6-120">參考</span><span class="sxs-lookup"><span data-stu-id="e40a6-120">References</span></span>

- <span data-ttu-id="e40a6-121">量子邏輯電路的合成 Vivek V. Shende、Stephen S. Bullock、Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="e40a6-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="e40a6-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e40a6-122">See Also</span></span>

- [<span data-ttu-id="e40a6-123">Canon. ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="e40a6-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)