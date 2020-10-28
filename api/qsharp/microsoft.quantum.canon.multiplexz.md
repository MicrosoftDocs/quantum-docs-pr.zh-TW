---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: MultiplexZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: f7b1973e18ad396ebe892ad63ae47374a7cafbd5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698954"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="22950-102">MultiplexZ 操作</span><span class="sxs-lookup"><span data-stu-id="22950-102">MultiplexZ operation</span></span>

<span data-ttu-id="22950-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="22950-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="22950-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22950-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22950-105">在量子位的陣列上套用 Pauli Z 旋轉。</span><span class="sxs-lookup"><span data-stu-id="22950-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="22950-106">描述</span><span class="sxs-lookup"><span data-stu-id="22950-106">Description</span></span>

<span data-ttu-id="22950-107">這會套用由 $n $-量子位 number state $ \ket{j} $ 控制時，依角度 $ \ theta_j $ 對單一量子位 Pauli 運算子 $Z $ 執行旋轉的乘法受控制的單一作業。</span><span class="sxs-lookup"><span data-stu-id="22950-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="22950-108">尤其是，這項作業可以由單一</span><span class="sxs-lookup"><span data-stu-id="22950-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="22950-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}。</span><span class="sxs-lookup"><span data-stu-id="22950-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="22950-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="22950-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="22950-111">輸入</span><span class="sxs-lookup"><span data-stu-id="22950-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="22950-112">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="22950-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="22950-113">最多 $ 2 ^ n $ 係數 $ \ theta_j $ 的陣列。</span><span class="sxs-lookup"><span data-stu-id="22950-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="22950-114">$J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="22950-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="22950-115">控制項： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="22950-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="22950-116">以位元組由大到小的格式，$n $ 量子位 control register 編碼數位狀態 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="22950-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="22950-117">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="22950-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="22950-118">由 $e ^ {i P \ theta_j} $ 旋轉的單一量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="22950-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="22950-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22950-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="22950-120">備註</span><span class="sxs-lookup"><span data-stu-id="22950-120">Remarks</span></span>

<span data-ttu-id="22950-121">`coefficients` 如果指定了少於 $ 2 ^ n $ 的元素，則會以 $ \ theta_j = $0.0 填補。</span><span class="sxs-lookup"><span data-stu-id="22950-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="22950-122">參考</span><span class="sxs-lookup"><span data-stu-id="22950-122">References</span></span>

- <span data-ttu-id="22950-123">量子邏輯電路的合成 Vivek V. Shende、Stephen S. Bullock、Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="22950-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="22950-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="22950-124">See Also</span></span>

- [<span data-ttu-id="22950-125">Canon. ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="22950-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)