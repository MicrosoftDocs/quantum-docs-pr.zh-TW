---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: ApproximatelyPrepareArbitraryState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 2561b098c5faf2d24bb9ab348fb052025808e441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700742"
---
# <a name="approximatelypreparearbitrarystate-operation"></a><span data-ttu-id="3f540-102">ApproximatelyPrepareArbitraryState 操作</span><span class="sxs-lookup"><span data-stu-id="3f540-102">ApproximatelyPrepareArbitraryState operation</span></span>

<span data-ttu-id="3f540-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3f540-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3f540-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f540-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f540-105">假設有一組係數和位元組由小到大編碼的量子暫存器，請在該暫存器上備妥指定係數所描述的狀態，直到指定的近似值容錯。</span><span class="sxs-lookup"><span data-stu-id="3f540-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="3f540-106">描述</span><span class="sxs-lookup"><span data-stu-id="3f540-106">Description</span></span>

<span data-ttu-id="3f540-107">這種作業會準備具有複雜係數 $r _j e ^ {i t_j} $ 的任意量子狀態 $ \ket{\psi} $，$n $-量子位計算基礎狀態 $ \ket{0 \cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="3f540-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="3f540-108">尤其是，這項作業的動作可以透過單一轉換 $U $ 來模擬，而這會在全-零的狀態下運作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3f540-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="3f540-109">$ $ \begin{align} U\ket {0 ... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="3f540-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="3f540-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3f540-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="3f540-111">輸入</span><span class="sxs-lookup"><span data-stu-id="3f540-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="3f540-112">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3f540-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3f540-113">準備指定的狀態時，所要使用的近似值容錯。</span><span class="sxs-lookup"><span data-stu-id="3f540-113">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="3f540-114">係數： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="3f540-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="3f540-115">最多 $ 2 ^ n $ 複雜係數的陣列，以絕對值和階段 $ (r_j，t_j) $ 表示。</span><span class="sxs-lookup"><span data-stu-id="3f540-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="3f540-116">$J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="3f540-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="3f540-117">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f540-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3f540-118">以位元組由大到小的格式量子位註冊編碼編號狀態。</span><span class="sxs-lookup"><span data-stu-id="3f540-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="3f540-119">這應該會在計算基礎狀態 $ \ket{0...0} $ 中初始化。</span><span class="sxs-lookup"><span data-stu-id="3f540-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f540-120">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f540-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3f540-121">備註</span><span class="sxs-lookup"><span data-stu-id="3f540-121">Remarks</span></span>

<span data-ttu-id="3f540-122">負輸入係數 $r _j < $0 將被視為具有值 $ | r_j | $ 的正值。</span><span class="sxs-lookup"><span data-stu-id="3f540-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="3f540-123">`coefficients` 將會以 $ (r_j、t_j) = (0.0、0.0) $ 的元素填補，以指定小於 $ 2 ^ n $。</span><span class="sxs-lookup"><span data-stu-id="3f540-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="3f540-124">參考</span><span class="sxs-lookup"><span data-stu-id="3f540-124">References</span></span>

- <span data-ttu-id="3f540-125">量子邏輯電路的合成 Vivek V. Shende、Stephen S. Bullock、Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="3f540-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="3f540-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3f540-126">See Also</span></span>

- [<span data-ttu-id="3f540-127">ApproximatelyPrepareArbitraryState。</span><span class="sxs-lookup"><span data-stu-id="3f540-127">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)