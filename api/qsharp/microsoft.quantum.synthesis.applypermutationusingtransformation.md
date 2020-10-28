---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: ApplyPermutationUsingTransformation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: b7196c592690a00da49b17f52b30536ba97b6035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701086"
---
# <a name="applypermutationusingtransformation-operation"></a><span data-ttu-id="609da-102">ApplyPermutationUsingTransformation 操作</span><span class="sxs-lookup"><span data-stu-id="609da-102">ApplyPermutationUsingTransformation operation</span></span>

<span data-ttu-id="609da-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="609da-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="609da-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="609da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="609da-105">使用以轉換為基礎的合成排列，在量子狀態中 Permutes amplitudes。</span><span class="sxs-lookup"><span data-stu-id="609da-105">Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="609da-106">描述</span><span class="sxs-lookup"><span data-stu-id="609da-106">Description</span></span>

<span data-ttu-id="609da-107">此程式會實行單向轉換型合成方法。</span><span class="sxs-lookup"><span data-stu-id="609da-107">This procedure implements the unidirectional transformation based synthesis approach.</span></span>  <span data-ttu-id="609da-108">輸入是一個排列 $ \pi $ over $ 2 ^ n $ elements $ \{ 0，\dots ..，2 ^ n-1 \} $，代表 $n $-variable 可還原的布耳函數。</span><span class="sxs-lookup"><span data-stu-id="609da-108">Input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="609da-109">演算法會反復執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="609da-109">The algorithm performs iteratively the following steps:</span></span>

1. <span data-ttu-id="609da-110">尋找最小的 $x $，$x \ne \pi (x) = y $。</span><span class="sxs-lookup"><span data-stu-id="609da-110">Find smallest $x$ such that $x \ne \pi(x) = y$.</span></span>
2. <span data-ttu-id="609da-111">尋找多個控制的 Toffoli 作業（套用至輸出）會將 $ \pi (x) = x $，而不會變更所有 $x ' < x $ 的 $ \pi (x ' ) $</span><span class="sxs-lookup"><span data-stu-id="609da-111">Find multiple-controlled Toffoli operations, which applied to the outputs make $\pi(x) = x$ and do not change $\pi(x')$ for all $x' < x$</span></span>

## <a name="input"></a><span data-ttu-id="609da-112">輸入</span><span class="sxs-lookup"><span data-stu-id="609da-112">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="609da-113">為永久： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="609da-113">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="609da-114">從0開始的 $ 2 ^ n $ 元素排列。</span><span class="sxs-lookup"><span data-stu-id="609da-114">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="609da-115">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="609da-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="609da-116">套用排列之 $n $ 量子位的清單。</span><span class="sxs-lookup"><span data-stu-id="609da-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="609da-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="609da-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="609da-118">參考</span><span class="sxs-lookup"><span data-stu-id="609da-118">References</span></span>

- [<span data-ttu-id="609da-119">*D. Michael 莎莎* 、 *Dmitri Maslov* 、 *GERHARD Dueck* 、Proc. DAC 2003、IEEE、pp 318-323、2003</span><span class="sxs-lookup"><span data-stu-id="609da-119">*D. Michael Miller* , *Dmitri Maslov* , *Gerhard W. Dueck* , Proc. DAC 2003, IEEE, pp. 318-323, 2003</span></span>](https://doi.org/10.1145/775832.775915)
- [<span data-ttu-id="609da-120">*Mathias Soeken* 、 *Gerhard Dueck* 、 *d. Michael 莎莎* 、Proc 2016、springer link、pp 307-321、2016</span><span class="sxs-lookup"><span data-stu-id="609da-120">*Mathias Soeken* , *Gerhard W. Dueck* , *D. Michael Miller* , Proc. RC 2016, Springer, pp. 307-321, 2016</span></span>](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a><span data-ttu-id="609da-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="609da-121">See Also</span></span>

- [<span data-ttu-id="609da-122">ApplyPermutationUsingDecomposition。</span><span class="sxs-lookup"><span data-stu-id="609da-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)