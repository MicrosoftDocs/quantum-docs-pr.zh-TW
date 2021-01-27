---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 081541d93bf853fa0de1573038dc00c296432281
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855852"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="a8ca7-102">StatePreparationPositiveCoefficients 函式</span><span class="sxs-lookup"><span data-stu-id="a8ca7-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="a8ca7-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a8ca7-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a8ca7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8ca7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="a8ca7-105">StatePreparationPositiveCoefficients 已被取代。</span><span class="sxs-lookup"><span data-stu-id="a8ca7-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="a8ca7-106">請改用 <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD>。</span><span class="sxs-lookup"><span data-stu-id="a8ca7-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="a8ca7-107">傳回可準備指定量子狀態的作業。</span><span class="sxs-lookup"><span data-stu-id="a8ca7-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="a8ca7-108">傳回的作業 $U $ 會從 $n $-量子位計算基礎狀態 $ \ket{0...0} $ 準備任意的量子狀態 $ \ket{\psi} $，其正係數 $ \ Alpha_j \ge $0。</span><span class="sxs-lookup"><span data-stu-id="a8ca7-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="a8ca7-109">在新配置的暫存器上執行的動作是由 $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ Alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ Alpha_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="a8ca7-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="a8ca7-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a8ca7-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="a8ca7-111">輸入</span><span class="sxs-lookup"><span data-stu-id="a8ca7-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="a8ca7-112">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a8ca7-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a8ca7-113">最多 $ 2 ^ n $ 係數 $ \ Alpha_j $ 的陣列。</span><span class="sxs-lookup"><span data-stu-id="a8ca7-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="a8ca7-114">$J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="a8ca7-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="a8ca7-115">輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a8ca7-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a8ca7-116">狀態準備單一作業 $U $。</span><span class="sxs-lookup"><span data-stu-id="a8ca7-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="a8ca7-117">範例</span><span class="sxs-lookup"><span data-stu-id="a8ca7-117">Example</span></span>

<span data-ttu-id="a8ca7-118">下列程式碼片段會準備量子位註冊中的量子狀態 $ \ket{\psi} = \ sqrt {1/8} \ ket {0} + \ sqrt {7/8} \ ket {2} $ `qubitsLE` 。</span><span class="sxs-lookup"><span data-stu-id="a8ca7-118">The following snippet prepares the quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let op = StatePreparationPositiveCoefficients(amplitudes);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="a8ca7-119">備註</span><span class="sxs-lookup"><span data-stu-id="a8ca7-119">Remarks</span></span>

<span data-ttu-id="a8ca7-120">負輸入係數 $ \ Alpha_j < $0 將視為具有值 $ | \ Alpha_j | $ 的正值。</span><span class="sxs-lookup"><span data-stu-id="a8ca7-120">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="a8ca7-121">`coefficients` 如果指定了少於 $ 2 ^ n $ 的元素，則會以 $ \ Alpha_j = $0.0 填補。</span><span class="sxs-lookup"><span data-stu-id="a8ca7-121">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>