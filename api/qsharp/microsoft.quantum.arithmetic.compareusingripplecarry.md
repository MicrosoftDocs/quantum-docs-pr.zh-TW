---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: e2d6e5a663f8c4e101c7e2ab1346d10cade3f4e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223454"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="0c825-102">CompareUsingRippleCarry 操作</span><span class="sxs-lookup"><span data-stu-id="0c825-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="0c825-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0c825-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0c825-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0c825-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0c825-105">這項作業會測試量子位暫存器所代表的整數是否大於另一個整數，並將結果的 XOR 套用至輸出量子位。</span><span class="sxs-lookup"><span data-stu-id="0c825-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="0c825-106">描述</span><span class="sxs-lookup"><span data-stu-id="0c825-106">Description</span></span>

<span data-ttu-id="0c825-107">如果有兩個整數， `x` 並 `y` 儲存在大小相同的量子位暫存器中，此作業就會檢查它們是否符合 `x > y` 。</span><span class="sxs-lookup"><span data-stu-id="0c825-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="0c825-108">若為 true，則會將1進行 xor 成輸出量子位。</span><span class="sxs-lookup"><span data-stu-id="0c825-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="0c825-109">否則，會將0進行 xor 到輸出量子位中。</span><span class="sxs-lookup"><span data-stu-id="0c825-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="0c825-110">換句話說，這項作業可以用單一 $ $ \begin{align} U\ket {x} \ ket {y} \ ket {z} = \ket{x}\ket{y}\ket{z\oplus (x>y) } 來表示。</span><span class="sxs-lookup"><span data-stu-id="0c825-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="0c825-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="0c825-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="0c825-112">輸入</span><span class="sxs-lookup"><span data-stu-id="0c825-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="0c825-113">x： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0c825-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0c825-114">要在量子位暫存器中以格式儲存的第一個數位 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="0c825-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="0c825-115">y： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0c825-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0c825-116">要在量子位暫存器中以格式儲存的第二個數字 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="0c825-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="0c825-117">輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0c825-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0c825-118">儲存比較 $x 結果>y $ 的量子位。</span><span class="sxs-lookup"><span data-stu-id="0c825-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c825-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c825-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="0c825-120">參考</span><span class="sxs-lookup"><span data-stu-id="0c825-120">References</span></span>

- <span data-ttu-id="0c825-121">新的量子 ripple-攜帶加法斷路 Steven A. Cuccaro、Thomas G. Draper、Samuel A. Kutin、David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="0c825-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>