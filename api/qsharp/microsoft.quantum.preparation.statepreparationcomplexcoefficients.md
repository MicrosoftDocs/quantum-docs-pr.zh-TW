---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 02e3d2fcf21b5bb4ed1bf7aa931597f918a1d369
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700406"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="34b6d-102">StatePreparationComplexCoefficients 函式</span><span class="sxs-lookup"><span data-stu-id="34b6d-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="34b6d-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="34b6d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="34b6d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="34b6d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="34b6d-105">傳回準備特定量子狀態的作業。</span><span class="sxs-lookup"><span data-stu-id="34b6d-105">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="34b6d-106">傳回的作業 $U $ 會準備具有複雜係數的任意量子狀態 $ \ket{\psi} $ $r _j e ^ {i t_j} $，從 $n $-量子位計算基礎狀態 $ \ket{0...0} $。</span><span class="sxs-lookup"><span data-stu-id="34b6d-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="34b6d-107">以 $ $ \begin{align} U\ket {0 ... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}} 為新配置的暫存器提供的動作。</span><span class="sxs-lookup"><span data-stu-id="34b6d-107">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="34b6d-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="34b6d-108">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="34b6d-109">輸入</span><span class="sxs-lookup"><span data-stu-id="34b6d-109">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="34b6d-110">係數： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="34b6d-110">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="34b6d-111">最多 $ 2 ^ n $ 複雜係數的陣列，以絕對值和階段 $ (r_j，t_j) $ 表示。</span><span class="sxs-lookup"><span data-stu-id="34b6d-111">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="34b6d-112">$J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="34b6d-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="34b6d-113">輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="34b6d-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="34b6d-114">狀態準備單一作業 $U $。</span><span class="sxs-lookup"><span data-stu-id="34b6d-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="34b6d-115">備註</span><span class="sxs-lookup"><span data-stu-id="34b6d-115">Remarks</span></span>

<span data-ttu-id="34b6d-116">負輸入係數 $r _j < $0 將被視為具有值 $ | r_j | $ 的正值。</span><span class="sxs-lookup"><span data-stu-id="34b6d-116">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="34b6d-117">`coefficients` 將會以 $ (r_j、t_j) = (0.0、0.0) $ 的元素填補，以指定小於 $ 2 ^ n $。</span><span class="sxs-lookup"><span data-stu-id="34b6d-117">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>