---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: aa5b63e058e1ea726b0d4c6eca73078831daaf3b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204686"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="e9cca-102">TrotterStepSize 函式</span><span class="sxs-lookup"><span data-stu-id="e9cca-102">TrotterStepSize function</span></span>

<span data-ttu-id="e9cca-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e9cca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e9cca-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9cca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9cca-105">計算 Trotter 模擬演算法的遞迴實 Trotter 步驟大小。</span><span class="sxs-lookup"><span data-stu-id="e9cca-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="e9cca-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e9cca-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="e9cca-107">order： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e9cca-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="e9cca-108">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e9cca-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="e9cca-109">備註</span><span class="sxs-lookup"><span data-stu-id="e9cca-109">Remarks</span></span>

<span data-ttu-id="e9cca-110">這項作業會使用與 [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139)不同的索引慣例。</span><span class="sxs-lookup"><span data-stu-id="e9cca-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="e9cca-111">尤其是，會 `DecomposedIntoTimeStepsCA(_, 4)` 對應到 quant-ph/0508139 中的純量 $p _2 ( \lambda) $。</span><span class="sxs-lookup"><span data-stu-id="e9cca-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>