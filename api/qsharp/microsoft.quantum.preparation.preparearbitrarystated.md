---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateD
title: PrepareArbitraryStateD 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: cca0ea16dca3f3da8ce76a43f1012ffa0e4a72e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210602"
---
# <a name="preparearbitrarystated-operation"></a><span data-ttu-id="d49b0-102">PrepareArbitraryStateD 操作</span><span class="sxs-lookup"><span data-stu-id="d49b0-102">PrepareArbitraryStateD operation</span></span>

<span data-ttu-id="d49b0-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d49b0-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d49b0-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d49b0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d49b0-105">假設有一組係數和位元組由小到大編碼的量子暫存器，請在該暫存器上備妥給定係數所描述的狀態。</span><span class="sxs-lookup"><span data-stu-id="d49b0-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryStateD (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d49b0-106">描述</span><span class="sxs-lookup"><span data-stu-id="d49b0-106">Description</span></span>

<span data-ttu-id="d49b0-107">這種作業會準備具有複雜係數 $r _j e ^ {i t_j} $ 的任意量子狀態 $ \ket{\psi} $，$n $-量子位計算基礎狀態 $ \ket{0 \cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="d49b0-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="d49b0-108">尤其是，這項作業的動作可以透過單一轉換 $U $ 來模擬，而此轉換會以零為的狀態來運作</span><span class="sxs-lookup"><span data-stu-id="d49b0-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ that acts on the all-zeros state as</span></span>

<span data-ttu-id="d49b0-109">$ $ \begin{align} U\ket {0 ... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="d49b0-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="d49b0-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d49b0-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="d49b0-111">輸入</span><span class="sxs-lookup"><span data-stu-id="d49b0-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="d49b0-112">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d49b0-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d49b0-113">最多 $ 2 ^ n $ 實數係數的陣列。</span><span class="sxs-lookup"><span data-stu-id="d49b0-113">Array of up to $2^n$ real coefficients.</span></span> <span data-ttu-id="d49b0-114">$J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="d49b0-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="d49b0-115">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d49b0-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d49b0-116">以位元組由大到小的格式量子位註冊編碼編號狀態。</span><span class="sxs-lookup"><span data-stu-id="d49b0-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="d49b0-117">這應該會在計算基礎狀態 $ \ket{0...0} $ 中初始化。</span><span class="sxs-lookup"><span data-stu-id="d49b0-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d49b0-118">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d49b0-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d49b0-119">備註</span><span class="sxs-lookup"><span data-stu-id="d49b0-119">Remarks</span></span>

<span data-ttu-id="d49b0-120">負輸入係數 $r _j < $0 將被視為具有值 $ | r_j | $ 的正值。</span><span class="sxs-lookup"><span data-stu-id="d49b0-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="d49b0-121">`coefficients` 將會以 $ (r_j、t_j) = (0.0、0.0) $ 的元素填補，以指定小於 $ 2 ^ n $。</span><span class="sxs-lookup"><span data-stu-id="d49b0-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="d49b0-122">參考</span><span class="sxs-lookup"><span data-stu-id="d49b0-122">References</span></span>

- <span data-ttu-id="d49b0-123">量子邏輯電路的合成 Vivek V. Shende、Stephen S. Bullock、Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="d49b0-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="d49b0-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d49b0-124">See Also</span></span>

- [<span data-ttu-id="d49b0-125">ApproximatelyPrepareArbitraryState。</span><span class="sxs-lookup"><span data-stu-id="d49b0-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)