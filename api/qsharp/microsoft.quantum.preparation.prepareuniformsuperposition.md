---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697147"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="21c49-102">PrepareUniformSuperposition 操作</span><span class="sxs-lookup"><span data-stu-id="21c49-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="21c49-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="21c49-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="21c49-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="21c49-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="21c49-105">建立以0至編碼之狀態的統一迭加 `nIndices - 1` 。</span><span class="sxs-lookup"><span data-stu-id="21c49-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="21c49-106">亦即，這個單一 $U $ 會根據指定的輸入狀態 $ \ket{0\cdots 0} $，在所有數位狀態 $0 $ 到 $M-$1 的情況下建立統一迭加。</span><span class="sxs-lookup"><span data-stu-id="21c49-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="21c49-107">換句話說，$ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}。</span><span class="sxs-lookup"><span data-stu-id="21c49-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="21c49-108">\end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="21c49-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="21c49-109">輸入</span><span class="sxs-lookup"><span data-stu-id="21c49-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="21c49-110">nIndices： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="21c49-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="21c49-111">在統一迭加中，所需的狀態數目 $M $。</span><span class="sxs-lookup"><span data-stu-id="21c49-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="21c49-112">indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="21c49-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="21c49-113">以格式儲存數位狀態的量子位暫存器 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="21c49-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="21c49-114">此暫存器必須能夠儲存 $M-$1 的數位，並假設在 state $ \ket{0\cdots 0} $ 中初始化。</span><span class="sxs-lookup"><span data-stu-id="21c49-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="21c49-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="21c49-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="21c49-116">備註</span><span class="sxs-lookup"><span data-stu-id="21c49-116">Remarks</span></span>

<span data-ttu-id="21c49-117">作業是 adjointable 的，但在 `indexRegister` `nIndices` 這種情況下，必須在統一迭加中。</span><span class="sxs-lookup"><span data-stu-id="21c49-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>