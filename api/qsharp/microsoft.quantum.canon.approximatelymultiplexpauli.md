---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: ApproximatelyMultiplexPauli 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: c91937d9e82a2a1514d81529adb35a5f804a0e13
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699112"
---
# <a name="approximatelymultiplexpauli-operation"></a><span data-ttu-id="beb02-102">ApproximatelyMultiplexPauli 操作</span><span class="sxs-lookup"><span data-stu-id="beb02-102">ApproximatelyMultiplexPauli operation</span></span>

<span data-ttu-id="beb02-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="beb02-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="beb02-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="beb02-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="beb02-105">在量子位陣列上套用 Pauli 旋轉，並根據指定的承受度截斷小旋轉角度。</span><span class="sxs-lookup"><span data-stu-id="beb02-105">Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="beb02-106">描述</span><span class="sxs-lookup"><span data-stu-id="beb02-106">Description</span></span>

<span data-ttu-id="beb02-107">這會套用一個受控制的單一作業，此作業會在由 $n $-量子位 number state $ \ket{j} $ 控制時，對單一量子位 Pauli 運算子 $P $ 執行旋轉（依角度 $ \ theta_j $）。</span><span class="sxs-lookup"><span data-stu-id="beb02-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="beb02-108">尤其是這項作業的動作是由單一</span><span class="sxs-lookup"><span data-stu-id="beb02-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="beb02-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}。</span><span class="sxs-lookup"><span data-stu-id="beb02-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="beb02-110">\end{align}</span><span class="sxs-lookup"><span data-stu-id="beb02-110">\end{align}</span></span>

##

## <a name="input"></a><span data-ttu-id="beb02-111">輸入</span><span class="sxs-lookup"><span data-stu-id="beb02-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="beb02-112">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="beb02-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="beb02-113">低於的容錯會被截斷。</span><span class="sxs-lookup"><span data-stu-id="beb02-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="beb02-114">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="beb02-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="beb02-115">最多 $ 2 ^ n $ 係數 $ \ theta_j $ 的陣列。</span><span class="sxs-lookup"><span data-stu-id="beb02-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="beb02-116">$J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="beb02-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="beb02-117">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="beb02-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="beb02-118">Pauli 運算子 $P $，可決定旋轉軸。</span><span class="sxs-lookup"><span data-stu-id="beb02-118">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="beb02-119">控制項： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="beb02-119">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="beb02-120">以位元組由大到小的格式，$n $ 量子位 control register 編碼數位狀態 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="beb02-120">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="beb02-121">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="beb02-121">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="beb02-122">由 $e ^ {i P \ theta_j} $ 旋轉的單一量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="beb02-122">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="beb02-123">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="beb02-123">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="beb02-124">備註</span><span class="sxs-lookup"><span data-stu-id="beb02-124">Remarks</span></span>

<span data-ttu-id="beb02-125">`coefficients` 如果指定了少於 $ 2 ^ n $ 的元素，則會以 $ \ theta_j = $0.0 填補。</span><span class="sxs-lookup"><span data-stu-id="beb02-125">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="beb02-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="beb02-126">See Also</span></span>

- [<span data-ttu-id="beb02-127">Canon. MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="beb02-127">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)