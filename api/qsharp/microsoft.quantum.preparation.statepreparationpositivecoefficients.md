---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700402"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="9add3-102">StatePreparationPositiveCoefficients 函式</span><span class="sxs-lookup"><span data-stu-id="9add3-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="9add3-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="9add3-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="9add3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9add3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9add3-105">傳回可準備指定量子狀態的作業。</span><span class="sxs-lookup"><span data-stu-id="9add3-105">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="9add3-106">傳回的作業 $U $ 會從 $n $-量子位計算基礎狀態 $ \ket{0...0} $ 準備任意的量子狀態 $ \ket{\psi} $，其正係數 $ \ Alpha_j \ge $0。</span><span class="sxs-lookup"><span data-stu-id="9add3-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="9add3-107">在新配置的暫存器上執行的動作是由 $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ Alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ Alpha_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="9add3-107">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="9add3-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9add3-108">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="9add3-109">輸入</span><span class="sxs-lookup"><span data-stu-id="9add3-109">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="9add3-110">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9add3-110">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9add3-111">最多 $ 2 ^ n $ 係數 $ \ Alpha_j $ 的陣列。</span><span class="sxs-lookup"><span data-stu-id="9add3-111">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="9add3-112">$J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="9add3-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="9add3-113">輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="9add3-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="9add3-114">狀態準備單一作業 $U $。</span><span class="sxs-lookup"><span data-stu-id="9add3-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="9add3-115">備註</span><span class="sxs-lookup"><span data-stu-id="9add3-115">Remarks</span></span>

<span data-ttu-id="9add3-116">負輸入係數 $ \ Alpha_j < $0 將視為具有值 $ | \ Alpha_j | $ 的正值。</span><span class="sxs-lookup"><span data-stu-id="9add3-116">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="9add3-117">`coefficients` 如果指定了少於 $ 2 ^ n $ 的元素，則會以 $ \ Alpha_j = $0.0 填補。</span><span class="sxs-lookup"><span data-stu-id="9add3-117">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>