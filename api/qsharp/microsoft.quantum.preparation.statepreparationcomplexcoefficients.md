---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 1d0efa7b83d2e8e75c4b293866f3929f357ec44b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210364"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="f382b-102">StatePreparationComplexCoefficients 函式</span><span class="sxs-lookup"><span data-stu-id="f382b-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="f382b-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f382b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f382b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f382b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="f382b-105">StatePreparationComplexCoefficients 已被取代。</span><span class="sxs-lookup"><span data-stu-id="f382b-105">StatePreparationComplexCoefficients has been deprecated.</span></span> <span data-ttu-id="f382b-106">請改用 <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP>。</span><span class="sxs-lookup"><span data-stu-id="f382b-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="f382b-107">傳回準備特定量子狀態的作業。</span><span class="sxs-lookup"><span data-stu-id="f382b-107">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="f382b-108">傳回的作業 $U $ 會準備具有複雜係數的任意量子狀態 $ \ket{\psi} $ $r _j e ^ {i t_j} $，從 $n $-量子位計算基礎狀態 $ \ket{0...0} $。</span><span class="sxs-lookup"><span data-stu-id="f382b-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="f382b-109">以 $ $ \begin{align} U\ket {0 ... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}} 為新配置的暫存器提供的動作。</span><span class="sxs-lookup"><span data-stu-id="f382b-109">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="f382b-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f382b-110">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="f382b-111">輸入</span><span class="sxs-lookup"><span data-stu-id="f382b-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="f382b-112">係數： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="f382b-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="f382b-113">最多 $ 2 ^ n $ 複雜係數的陣列，以絕對值和階段 $ (r_j，t_j) $ 表示。</span><span class="sxs-lookup"><span data-stu-id="f382b-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="f382b-114">$J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="f382b-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="f382b-115">輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="f382b-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f382b-116">狀態準備單一作業 $U $。</span><span class="sxs-lookup"><span data-stu-id="f382b-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="f382b-117">備註</span><span class="sxs-lookup"><span data-stu-id="f382b-117">Remarks</span></span>

<span data-ttu-id="f382b-118">負輸入係數 $r _j < $0 將被視為具有值 $ | r_j | $ 的正值。</span><span class="sxs-lookup"><span data-stu-id="f382b-118">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="f382b-119">`coefficients` 將會以 $ (r_j、t_j) = (0.0、0.0) $ 的元素填補，以指定小於 $ 2 ^ n $。</span><span class="sxs-lookup"><span data-stu-id="f382b-119">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>