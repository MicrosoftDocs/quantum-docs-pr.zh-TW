---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: PrepareArbitraryState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > PrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 18a1e86f8e110a8f48d7dd50961e1f1f471ffc4e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190694"
---
# <a name="preparearbitrarystate-operation"></a><span data-ttu-id="ad785-102">PrepareArbitraryState 操作</span><span class="sxs-lookup"><span data-stu-id="ad785-102">PrepareArbitraryState operation</span></span>

<span data-ttu-id="ad785-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="ad785-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="ad785-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad785-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="ad785-105">PrepareArbitraryState 已被取代。</span><span class="sxs-lookup"><span data-stu-id="ad785-105">PrepareArbitraryState has been deprecated.</span></span> <span data-ttu-id="ad785-106">請改用 <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP>。</span><span class="sxs-lookup"><span data-stu-id="ad785-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="ad785-107">假設有一組係數和位元組由小到大編碼的量子暫存器，請在該暫存器上備妥給定係數所描述的狀態。</span><span class="sxs-lookup"><span data-stu-id="ad785-107">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ad785-108">描述</span><span class="sxs-lookup"><span data-stu-id="ad785-108">Description</span></span>

<span data-ttu-id="ad785-109">這種作業會準備具有複雜係數 $r _j e ^ {i t_j} $ 的任意量子狀態 $ \ket{\psi} $，$n $-量子位計算基礎狀態 $ \ket{0 \cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="ad785-109">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="ad785-110">尤其是，這項作業的動作可以透過單一轉換 $U $ 來模擬，而這會在全-零的狀態下運作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ad785-110">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="ad785-111">$ $ \begin{align} U\ket {0 ... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="ad785-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="ad785-112">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="ad785-112">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="ad785-113">輸入</span><span class="sxs-lookup"><span data-stu-id="ad785-113">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="ad785-114">係數： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="ad785-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="ad785-115">最多 $ 2 ^ n $ 複雜係數的陣列，以絕對值和階段 $ (r_j，t_j) $ 表示。</span><span class="sxs-lookup"><span data-stu-id="ad785-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="ad785-116">$J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="ad785-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="ad785-117">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ad785-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ad785-118">以位元組由大到小的格式量子位註冊編碼編號狀態。</span><span class="sxs-lookup"><span data-stu-id="ad785-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="ad785-119">這應該會在計算基礎狀態 $ \ket{0...0} $ 中初始化。</span><span class="sxs-lookup"><span data-stu-id="ad785-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad785-120">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad785-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ad785-121">備註</span><span class="sxs-lookup"><span data-stu-id="ad785-121">Remarks</span></span>

<span data-ttu-id="ad785-122">負輸入係數 $r _j < $0 將被視為具有值 $ | r_j | $ 的正值。</span><span class="sxs-lookup"><span data-stu-id="ad785-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="ad785-123">`coefficients` 將會以 $ (r_j、t_j) = (0.0、0.0) $ 的元素填補，以指定小於 $ 2 ^ n $。</span><span class="sxs-lookup"><span data-stu-id="ad785-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="ad785-124">參考</span><span class="sxs-lookup"><span data-stu-id="ad785-124">References</span></span>

- <span data-ttu-id="ad785-125">量子邏輯電路的合成 Vivek V. Shende、Stephen S. Bullock、Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="ad785-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="ad785-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ad785-126">See Also</span></span>

- [<span data-ttu-id="ad785-127">ApproximatelyPrepareArbitraryState。</span><span class="sxs-lookup"><span data-stu-id="ad785-127">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)