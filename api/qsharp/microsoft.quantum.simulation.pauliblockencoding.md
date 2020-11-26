---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: b1df6d239e6ef061cf0a4784c652e9dd126991d5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230424"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="905ad-102">PauliBlockEncoding 函式</span><span class="sxs-lookup"><span data-stu-id="905ad-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="905ad-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="905ad-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="905ad-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="905ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="905ad-105">針對 Hamiltonian 建立單一區塊編碼。</span><span class="sxs-lookup"><span data-stu-id="905ad-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="905ad-106">Hamiltonian $H = \ sum_ {j} \ Alpha_j P_j $ 會以 Pauli 詞彙 $P _j $ 的總和描述，每個詞彙都有實際係數 $ \ Alpha_j $。</span><span class="sxs-lookup"><span data-stu-id="905ad-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="905ad-107">輸入</span><span class="sxs-lookup"><span data-stu-id="905ad-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="905ad-108">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="905ad-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="905ad-109">`GeneratorSystem`，描述 $H $ 作為 Pauli 詞彙的總和</span><span class="sxs-lookup"><span data-stu-id="905ad-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="905ad-110">輸出： ([雙精度浮點數](xref:microsoft.quantum.lang-ref.double)，[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)) </span><span class="sxs-lookup"><span data-stu-id="905ad-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="905ad-111">第一個參數</span><span class="sxs-lookup"><span data-stu-id="905ad-111">First parameter</span></span>

<span data-ttu-id="905ad-112">係數 $ \Alpha = \ sum_ {j} | \ Alpha_j | $ 的一個標準。</span><span class="sxs-lookup"><span data-stu-id="905ad-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="905ad-113">第二個參數</span><span class="sxs-lookup"><span data-stu-id="905ad-113">Second parameter</span></span>

<span data-ttu-id="905ad-114">`BlockEncodingReflection`Hamiltonian $H $ 的單一 $U $。</span><span class="sxs-lookup"><span data-stu-id="905ad-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="905ad-115">因為這個單一的滿足 $U ^ 2 = I $，所以也是反映。</span><span class="sxs-lookup"><span data-stu-id="905ad-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="905ad-116">備註</span><span class="sxs-lookup"><span data-stu-id="905ad-116">Remarks</span></span>

<span data-ttu-id="905ad-117">這是藉由準備和 unpreparing 狀態 $ \ sum_ {j} \sqrt{\ Alpha_j/\Alpha}\ket{j} $ 來取得，並且會建立相乘控制的單一 <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> 和 <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> 。</span><span class="sxs-lookup"><span data-stu-id="905ad-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>