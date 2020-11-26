---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: ApproximatelyApplyDiagonalUnitary 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 0a05b8a5891977a08ee2ae6a996657c6a8f3d792
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217113"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="2f13f-102">ApproximatelyApplyDiagonalUnitary 操作</span><span class="sxs-lookup"><span data-stu-id="2f13f-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="2f13f-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2f13f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2f13f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f13f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f13f-105">將複雜階段的陣列套用至量子位註冊的數值基礎狀態，並根據指定的容錯來截斷小旋轉角度。</span><span class="sxs-lookup"><span data-stu-id="2f13f-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2f13f-106">描述</span><span class="sxs-lookup"><span data-stu-id="2f13f-106">Description</span></span>

<span data-ttu-id="2f13f-107">此作業會在 $n $ 量子位 number state $ \ket{j} $ 上，執行套用複雜階段 $e ^ {i \ theta_j} $ 的對角線。</span><span class="sxs-lookup"><span data-stu-id="2f13f-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="2f13f-108">尤其是，這項作業可以由單一</span><span class="sxs-lookup"><span data-stu-id="2f13f-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="2f13f-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}。</span><span class="sxs-lookup"><span data-stu-id="2f13f-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="2f13f-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="2f13f-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="2f13f-111">輸入</span><span class="sxs-lookup"><span data-stu-id="2f13f-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="2f13f-112">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2f13f-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2f13f-113">低於的容錯會被截斷。</span><span class="sxs-lookup"><span data-stu-id="2f13f-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="2f13f-114">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2f13f-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2f13f-115">最多 $ 2 ^ n $ 係數 $ \ theta_j $ 的陣列。</span><span class="sxs-lookup"><span data-stu-id="2f13f-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="2f13f-116">$J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="2f13f-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="2f13f-117">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2f13f-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2f13f-118">以位元組由大到小的格式，$n $ 量子位 control register 編碼數位狀態 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="2f13f-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f13f-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f13f-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2f13f-120">備註</span><span class="sxs-lookup"><span data-stu-id="2f13f-120">Remarks</span></span>

<span data-ttu-id="2f13f-121">`coefficients` 如果指定了少於 $ 2 ^ n $ 的元素，則會以 $ \ theta_j = $0.0 填補。</span><span class="sxs-lookup"><span data-stu-id="2f13f-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="2f13f-122">參考</span><span class="sxs-lookup"><span data-stu-id="2f13f-122">References</span></span>

- <span data-ttu-id="2f13f-123">量子邏輯電路的合成 Vivek V. Shende、Stephen S. Bullock、Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="2f13f-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="2f13f-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2f13f-124">See Also</span></span>

- [<span data-ttu-id="2f13f-125">Canon. ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="2f13f-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)