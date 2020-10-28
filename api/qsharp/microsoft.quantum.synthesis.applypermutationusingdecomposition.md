---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 40b51807da155c57c3fa8d740eff28ceef0a0ffc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701094"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="5c5a9-102">ApplyPermutationUsingDecomposition 操作</span><span class="sxs-lookup"><span data-stu-id="5c5a9-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="5c5a9-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="5c5a9-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="5c5a9-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c5a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c5a9-105">使用以分解為基礎的合成排列，在量子狀態中 Permutes amplitudes。</span><span class="sxs-lookup"><span data-stu-id="5c5a9-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="5c5a9-106">描述</span><span class="sxs-lookup"><span data-stu-id="5c5a9-106">Description</span></span>

<span data-ttu-id="5c5a9-107">此程式會實行以分解為基礎的合成方法。</span><span class="sxs-lookup"><span data-stu-id="5c5a9-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="5c5a9-108">輸入是一個排列 $ \pi $ over $ 2 ^ n $ elements $ \{ 0，\dots ..，2 ^ n-1 \} $，代表 $n $-variable 可還原的布耳函數。</span><span class="sxs-lookup"><span data-stu-id="5c5a9-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="5c5a9-109">演算法會針對每個變數索引反復執行下列步驟，$i $：</span><span class="sxs-lookup"><span data-stu-id="5c5a9-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="5c5a9-110">Compute $ ( # A1 \ pi_l，\ pi_r) ，\pi ' ) $，讓 $ \ pi_l $ 和 $ \ pi_r $ 的影像不會變更其專案中的位，而不是在 $i $ 和 $ \pi ' $ 的影像中變更位 $i $ 的元素。</span><span class="sxs-lookup"><span data-stu-id="5c5a9-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="5c5a9-111">Set $ \pi \leftarrow \pi ' $，並根據非固定點的元素，從 $ \ pi_l $ 和 $ \ pi_r $ 衍生事實資料表。</span><span class="sxs-lookup"><span data-stu-id="5c5a9-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="5c5a9-112">針對所有變數索引套用這些步驟之後，剩餘的排列 $ \pi $ 將會是身分識別，且會根據所收集的事實資料表和索引，使用作業來套用事實資料表控制 @"microsoft.quantum.intrinsic.x" 的作業 @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" 。</span><span class="sxs-lookup"><span data-stu-id="5c5a9-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="5c5a9-113">變數順序是 $0、\dots ..、n-$1。</span><span class="sxs-lookup"><span data-stu-id="5c5a9-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="5c5a9-114">自訂變數順序可以在作業中指定 @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" 。</span><span class="sxs-lookup"><span data-stu-id="5c5a9-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="5c5a9-115">輸入</span><span class="sxs-lookup"><span data-stu-id="5c5a9-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="5c5a9-116">為永久： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5c5a9-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5c5a9-117">從0開始的 $ 2 ^ n $ 元素排列。</span><span class="sxs-lookup"><span data-stu-id="5c5a9-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="5c5a9-118">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5c5a9-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5c5a9-119">套用排列之 $n $ 量子位的清單。</span><span class="sxs-lookup"><span data-stu-id="5c5a9-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5c5a9-120">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c5a9-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="5c5a9-121">參考</span><span class="sxs-lookup"><span data-stu-id="5c5a9-121">References</span></span>

- [<span data-ttu-id="5c5a9-122">*Alexis De Vos* 、 *Yvan Van Rentergem* 、進階。) 的通訊。 2 (2，2008，pp 183--200</span><span class="sxs-lookup"><span data-stu-id="5c5a9-122">*Alexis De Vos* , *Yvan Van Rentergem* , Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="5c5a9-123">*Mathias Soeken* 、 *劉娜 Tague* 、 *Gerhard W. Dueck* 、 *Rolf Drechsler* 、符號計算 73 (2016) 、pp 1--26</span><span class="sxs-lookup"><span data-stu-id="5c5a9-123">*Mathias Soeken* , *Laura Tague* , *Gerhard W. Dueck* , *Rolf Drechsler* , Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="5c5a9-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5c5a9-124">See Also</span></span>

- [<span data-ttu-id="5c5a9-125">ApplyPermutationUsingDecompositionWithVariableOrder。</span><span class="sxs-lookup"><span data-stu-id="5c5a9-125">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="5c5a9-126">ApplyPermutationUsingTransformation。</span><span class="sxs-lookup"><span data-stu-id="5c5a9-126">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)