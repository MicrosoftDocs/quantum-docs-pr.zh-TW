---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846499"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="1e6f7-102">MultiplyByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="1e6f7-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="1e6f7-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1e6f7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1e6f7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e6f7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e6f7-105">在量子位暫存器上以整數常數執行模組化乘法。</span><span class="sxs-lookup"><span data-stu-id="1e6f7-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="1e6f7-106">描述</span><span class="sxs-lookup"><span data-stu-id="1e6f7-106">Description</span></span>

<span data-ttu-id="1e6f7-107">讓我們 `modulus` 以 $N $ 和 `constMultiplier` by $a $ 表示。</span><span class="sxs-lookup"><span data-stu-id="1e6f7-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="1e6f7-108">然後，這項作業會根據計算基礎來執行下列對應所定義的單一作業： $ $ \begin{align} \ket{y} \mapsto \ket{ (\cdot y) \operatorname{mod} N} \end{align} $ $，適用于 $0 $ 和 $N-$1 之間的所有 $y $。</span><span class="sxs-lookup"><span data-stu-id="1e6f7-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="1e6f7-109">輸入</span><span class="sxs-lookup"><span data-stu-id="1e6f7-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="1e6f7-110">constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1e6f7-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1e6f7-111">乘以乘數的常數。</span><span class="sxs-lookup"><span data-stu-id="1e6f7-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="1e6f7-112">必須是與模數的共同質數。</span><span class="sxs-lookup"><span data-stu-id="1e6f7-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="1e6f7-113">模數： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1e6f7-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1e6f7-114">乘法運算會執行模數 `modulus` 。</span><span class="sxs-lookup"><span data-stu-id="1e6f7-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="1e6f7-115">乘數： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1e6f7-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1e6f7-116">要乘以常數的數位。</span><span class="sxs-lookup"><span data-stu-id="1e6f7-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="1e6f7-117">這是以位元組由小到大格式的整數量子位編碼的陣列。</span><span class="sxs-lookup"><span data-stu-id="1e6f7-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e6f7-118">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e6f7-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1e6f7-119">備註</span><span class="sxs-lookup"><span data-stu-id="1e6f7-119">Remarks</span></span>

- <span data-ttu-id="1e6f7-120">如需電路圖和說明，請參閱[arXiv： quant-ph/0205095V3 頁面 8](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)上的圖7。</span><span class="sxs-lookup"><span data-stu-id="1e6f7-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="1e6f7-121">此作業對應到[arXiv： quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)中的 u ₐ</span><span class="sxs-lookup"><span data-stu-id="1e6f7-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>