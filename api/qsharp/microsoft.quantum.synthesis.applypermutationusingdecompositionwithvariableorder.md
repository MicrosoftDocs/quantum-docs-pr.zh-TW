---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701087"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="9cc9d-102">ApplyPermutationUsingDecompositionWithVariableOrder 操作</span><span class="sxs-lookup"><span data-stu-id="9cc9d-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="9cc9d-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="9cc9d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="9cc9d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9cc9d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9cc9d-105">使用以分解為基礎的合成排列，在量子狀態中 Permutes amplitudes。</span><span class="sxs-lookup"><span data-stu-id="9cc9d-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="9cc9d-106">描述</span><span class="sxs-lookup"><span data-stu-id="9cc9d-106">Description</span></span>

<span data-ttu-id="9cc9d-107">這項作業是 @"microsoft.quantum.synthesis.applypermutationusingdecomposition" 可指定變數順序的一般版本。</span><span class="sxs-lookup"><span data-stu-id="9cc9d-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="9cc9d-108">不同的變數順序會變更分解順序，以及用於受控制閘道的事實資料表 @"microsoft.quantum.intrinsic.x" 。</span><span class="sxs-lookup"><span data-stu-id="9cc9d-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="9cc9d-109">因此，變更變數順序會變更用來實現排列的整體閘道數目。</span><span class="sxs-lookup"><span data-stu-id="9cc9d-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="9cc9d-110">輸入</span><span class="sxs-lookup"><span data-stu-id="9cc9d-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="9cc9d-111">為永久： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9cc9d-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9cc9d-112">從0開始的 $ 2 ^ n $ 元素排列。</span><span class="sxs-lookup"><span data-stu-id="9cc9d-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="9cc9d-113">variableOrder： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9cc9d-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9cc9d-114">從0開始的 $n $ 元素排列。</span><span class="sxs-lookup"><span data-stu-id="9cc9d-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="9cc9d-115">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9cc9d-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9cc9d-116">套用排列之 $n $ 量子位的清單。</span><span class="sxs-lookup"><span data-stu-id="9cc9d-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9cc9d-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9cc9d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9cc9d-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9cc9d-118">See Also</span></span>

- [<span data-ttu-id="9cc9d-119">ApplyPermutationUsingDecomposition。</span><span class="sxs-lookup"><span data-stu-id="9cc9d-119">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="9cc9d-120">ApplyPermutationUsingTransformation。</span><span class="sxs-lookup"><span data-stu-id="9cc9d-120">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)