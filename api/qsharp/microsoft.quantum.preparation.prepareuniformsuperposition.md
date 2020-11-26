---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 9b9f182ed7c1ea24ae74b8a2321a309042a17c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230084"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="b9d3e-102">PrepareUniformSuperposition 操作</span><span class="sxs-lookup"><span data-stu-id="b9d3e-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="b9d3e-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="b9d3e-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="b9d3e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9d3e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b9d3e-105">建立以0至編碼之狀態的統一迭加 `nIndices - 1` 。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="b9d3e-106">亦即，這個單一 $U $ 會根據指定的輸入狀態 $ \ket{0\cdots 0} $，在所有數位狀態 $0 $ 到 $M-$1 的情況下建立統一迭加。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="b9d3e-107">換句話說，$ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="b9d3e-108">\end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b9d3e-109">輸入</span><span class="sxs-lookup"><span data-stu-id="b9d3e-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="b9d3e-110">nIndices： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b9d3e-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b9d3e-111">在統一迭加中，所需的狀態數目 $M $。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="b9d3e-112">indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b9d3e-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b9d3e-113">以格式儲存數位狀態的量子位暫存器 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="b9d3e-114">此暫存器必須能夠儲存 $M-$1 的數位，並假設在 state $ \ket{0\cdots 0} $ 中初始化。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b9d3e-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b9d3e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b9d3e-116">備註</span><span class="sxs-lookup"><span data-stu-id="b9d3e-116">Remarks</span></span>

<span data-ttu-id="b9d3e-117">作業是 adjointable 的，但在 `indexRegister` `nIndices` 這種情況下，必須在統一迭加中。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>