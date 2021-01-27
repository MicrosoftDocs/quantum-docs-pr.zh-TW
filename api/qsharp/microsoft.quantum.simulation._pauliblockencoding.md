---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: c27ef1a6b7cd7c84defe2a783e9fb1610e52d1e7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851069"
---
# <a name="_pauliblockencoding-function"></a><span data-ttu-id="11061-102">_PauliBlockEncoding 函式</span><span class="sxs-lookup"><span data-stu-id="11061-102">_PauliBlockEncoding function</span></span>

<span data-ttu-id="11061-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="11061-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="11061-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="11061-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="11061-105">針對 Hamiltonian 建立單一區塊編碼。</span><span class="sxs-lookup"><span data-stu-id="11061-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="11061-106">Hamiltonian $H = \ sum_ {j} \ Alpha_j P_j $ 會以 Pauli 詞彙 $P _j $ 的總和描述，每個詞彙都有實際係數 $ \ Alpha_j $。</span><span class="sxs-lookup"><span data-stu-id="11061-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="11061-107">輸入</span><span class="sxs-lookup"><span data-stu-id="11061-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="11061-108">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="11061-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="11061-109">`GeneratorSystem`，描述 $H $ 作為 Pauli 詞彙的總和</span><span class="sxs-lookup"><span data-stu-id="11061-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>


### <a name="stateprepunitary--double---littleendian--unit--is-adj--ctl"></a><span data-ttu-id="11061-110">statePrepUnitary： [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="11061-110">statePrepUnitary : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="11061-111">單一作業 $V $，在指定函式 $f： j\rightarrow V_j $ 的情況下，套用在 index $ \ket{j} $ 上控制的單一 $V _j $。</span><span class="sxs-lookup"><span data-stu-id="11061-111">A unitary operation $V$ that applies the unitary $V_j$ controlled on index $\ket{j}$, given a function $f: j\rightarrow V_j$.</span></span>


### <a name="multiplexer--intint---qubit--unit--is-adj--ctl---littleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="11061-112">多工器： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int) -> [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit)  是形容詞 + ctl</span><span class="sxs-lookup"><span data-stu-id="11061-112">multiplexer : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>





## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="11061-113">輸出： ([雙精度浮點數](xref:microsoft.quantum.lang-ref.double)，[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)) </span><span class="sxs-lookup"><span data-stu-id="11061-113">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="11061-114">第一個參數</span><span class="sxs-lookup"><span data-stu-id="11061-114">First parameter</span></span>

<span data-ttu-id="11061-115">係數 $ \Alpha = \ sum_ {j} | \ Alpha_j | $ 的一個標準。</span><span class="sxs-lookup"><span data-stu-id="11061-115">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="11061-116">第二個參數</span><span class="sxs-lookup"><span data-stu-id="11061-116">Second parameter</span></span>

<span data-ttu-id="11061-117">`BlockEncodingReflection`Hamiltonian $U $ 的單一 $U $。</span><span class="sxs-lookup"><span data-stu-id="11061-117">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $U$.</span></span> <span data-ttu-id="11061-118">因為這個單一的滿足 $U ^ 2 = I $，所以也是反映。</span><span class="sxs-lookup"><span data-stu-id="11061-118">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="11061-119">備註</span><span class="sxs-lookup"><span data-stu-id="11061-119">Remarks</span></span>

<span data-ttu-id="11061-120">範例作業： prepare and unpreparing a state $ \ sum_ {j} \sqrt{\ Alpha_j/\Alpha}\ket{j} $，以及建立一個相乘控制的單一 <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> 和 <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> 。</span><span class="sxs-lookup"><span data-stu-id="11061-120">Example operations the prepare and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and construct a multiply-controlled unitary are <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>