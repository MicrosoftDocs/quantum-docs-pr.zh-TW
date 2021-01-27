---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848013"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="13167-102">PauliBlockEncoding 函式</span><span class="sxs-lookup"><span data-stu-id="13167-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="13167-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="13167-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="13167-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13167-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13167-105">針對 Hamiltonian 建立單一區塊編碼。</span><span class="sxs-lookup"><span data-stu-id="13167-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="13167-106">Hamiltonian $H = \ sum_ {j} \ Alpha_j P_j $ 會以 Pauli 詞彙 $P _j $ 的總和描述，每個詞彙都有實際係數 $ \ Alpha_j $。</span><span class="sxs-lookup"><span data-stu-id="13167-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="13167-107">輸入</span><span class="sxs-lookup"><span data-stu-id="13167-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="13167-108">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="13167-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="13167-109">`GeneratorSystem`，描述 $H $ 作為 Pauli 詞彙的總和</span><span class="sxs-lookup"><span data-stu-id="13167-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="13167-110">輸出： ([雙精度浮點數](xref:microsoft.quantum.lang-ref.double)，[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)) </span><span class="sxs-lookup"><span data-stu-id="13167-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="13167-111">第一個參數</span><span class="sxs-lookup"><span data-stu-id="13167-111">First parameter</span></span>

<span data-ttu-id="13167-112">係數 $ \Alpha = \ sum_ {j} | \ Alpha_j | $ 的一個標準。</span><span class="sxs-lookup"><span data-stu-id="13167-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="13167-113">第二個參數</span><span class="sxs-lookup"><span data-stu-id="13167-113">Second parameter</span></span>

<span data-ttu-id="13167-114">`BlockEncodingReflection`Hamiltonian $H $ 的單一 $U $。</span><span class="sxs-lookup"><span data-stu-id="13167-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="13167-115">因為這個單一的滿足 $U ^ 2 = I $，所以也是反映。</span><span class="sxs-lookup"><span data-stu-id="13167-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="13167-116">備註</span><span class="sxs-lookup"><span data-stu-id="13167-116">Remarks</span></span>

<span data-ttu-id="13167-117">這是藉由準備和 unpreparing 狀態 $ \ sum_ {j} \sqrt{\ Alpha_j/\Alpha}\ket{j} $ 來取得，並且會建立相乘控制的單一 <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> 和 <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> 。</span><span class="sxs-lookup"><span data-stu-id="13167-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>