---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: 842e7ded1e38f4f6e01e79d2758e30afb85dd349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699918"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="b2bc9-102">CompareUsingRippleCarry 操作</span><span class="sxs-lookup"><span data-stu-id="b2bc9-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="b2bc9-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b2bc9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b2bc9-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2bc9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2bc9-105">這項作業會測試量子位暫存器所代表的整數是否大於另一個整數，並將結果的 XOR 套用至輸出量子位。</span><span class="sxs-lookup"><span data-stu-id="b2bc9-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="b2bc9-106">描述</span><span class="sxs-lookup"><span data-stu-id="b2bc9-106">Description</span></span>

<span data-ttu-id="b2bc9-107">如果有兩個整數， `x` 並 `y` 儲存在大小相同的量子位暫存器中，此作業就會檢查它們是否符合 `x > y` 。</span><span class="sxs-lookup"><span data-stu-id="b2bc9-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="b2bc9-108">若為 true，則會將1進行 xor 成輸出量子位。</span><span class="sxs-lookup"><span data-stu-id="b2bc9-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="b2bc9-109">否則，會將0進行 xor 到輸出量子位中。</span><span class="sxs-lookup"><span data-stu-id="b2bc9-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="b2bc9-110">換句話說，這項作業可以用單一 $ $ \begin{align} U\ket {x} \ ket {y} \ ket {z} = \ket{x}\ket{y}\ket{z\oplus (x>y) } 來表示。</span><span class="sxs-lookup"><span data-stu-id="b2bc9-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="b2bc9-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b2bc9-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="b2bc9-112">輸入</span><span class="sxs-lookup"><span data-stu-id="b2bc9-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="b2bc9-113">x： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b2bc9-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b2bc9-114">要在量子位暫存器中以格式儲存的第一個數位 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="b2bc9-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="b2bc9-115">y： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b2bc9-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b2bc9-116">要在量子位暫存器中以格式儲存的第二個數字 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="b2bc9-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="b2bc9-117">輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b2bc9-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b2bc9-118">儲存比較 $x 結果>y $ 的量子位。</span><span class="sxs-lookup"><span data-stu-id="b2bc9-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2bc9-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2bc9-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="b2bc9-120">參考</span><span class="sxs-lookup"><span data-stu-id="b2bc9-120">References</span></span>

- <span data-ttu-id="b2bc9-121">新的量子 ripple-攜帶加法斷路 Steven A. Cuccaro、Thomas G. Draper、Samuel A. Kutin、David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="b2bc9-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>