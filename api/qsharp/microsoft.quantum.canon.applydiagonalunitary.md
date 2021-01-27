---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: ApplyDiagonalUnitary 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 14ab8d7beddda26594967225934d472d52bac9eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841894"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="bdc94-102">ApplyDiagonalUnitary 操作</span><span class="sxs-lookup"><span data-stu-id="bdc94-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="bdc94-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bdc94-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bdc94-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bdc94-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bdc94-105">將複雜階段的陣列套用至量子位註冊的數值基礎狀態。</span><span class="sxs-lookup"><span data-stu-id="bdc94-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="bdc94-106">描述</span><span class="sxs-lookup"><span data-stu-id="bdc94-106">Description</span></span>

<span data-ttu-id="bdc94-107">此作業會在 $n $ 量子位 number state $ \ket{j} $ 上，執行套用複雜階段 $e ^ {i \ theta_j} $ 的對角線。</span><span class="sxs-lookup"><span data-stu-id="bdc94-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="bdc94-108">尤其是，這項作業可以由單一</span><span class="sxs-lookup"><span data-stu-id="bdc94-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="bdc94-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}。</span><span class="sxs-lookup"><span data-stu-id="bdc94-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="bdc94-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="bdc94-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="bdc94-111">輸入</span><span class="sxs-lookup"><span data-stu-id="bdc94-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="bdc94-112">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bdc94-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bdc94-113">最多 $ 2 ^ n $ 係數 $ \ theta_j $ 的陣列。</span><span class="sxs-lookup"><span data-stu-id="bdc94-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="bdc94-114">$J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="bdc94-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="bdc94-115">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bdc94-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bdc94-116">以位元組由大到小的格式，$n $ 量子位 control register 編碼數位狀態 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="bdc94-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bdc94-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bdc94-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bdc94-118">備註</span><span class="sxs-lookup"><span data-stu-id="bdc94-118">Remarks</span></span>

<span data-ttu-id="bdc94-119">`coefficients` 如果指定了少於 $ 2 ^ n $ 的元素，則會以 $ \ theta_j = $0.0 填補。</span><span class="sxs-lookup"><span data-stu-id="bdc94-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="bdc94-120">參考資料</span><span class="sxs-lookup"><span data-stu-id="bdc94-120">References</span></span>

- <span data-ttu-id="bdc94-121">量子邏輯電路的合成 Vivek V. Shende、Stephen S. Bullock、Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="bdc94-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="bdc94-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bdc94-122">See Also</span></span>

- [<span data-ttu-id="bdc94-123">Canon. ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="bdc94-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)