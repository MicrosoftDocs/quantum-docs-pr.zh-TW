---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: fabfbff74572b3c96c701de5443e4265a0468d78
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698795"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="ec2db-102">TrotterStepSize 函式</span><span class="sxs-lookup"><span data-stu-id="ec2db-102">TrotterStepSize function</span></span>

<span data-ttu-id="ec2db-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ec2db-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ec2db-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ec2db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ec2db-105">計算 Trotter 模擬演算法的遞迴實 Trotter 步驟大小。</span><span class="sxs-lookup"><span data-stu-id="ec2db-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="ec2db-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ec2db-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="ec2db-107">order： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ec2db-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="ec2db-108">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ec2db-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="ec2db-109">備註</span><span class="sxs-lookup"><span data-stu-id="ec2db-109">Remarks</span></span>

<span data-ttu-id="ec2db-110">這項作業會使用與 [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139)不同的索引慣例。</span><span class="sxs-lookup"><span data-stu-id="ec2db-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="ec2db-111">尤其是，會 `DecomposedIntoTimeStepsCA(_, 4)` 對應到 quant-ph/0508139 中的純量 $p _2 ( \lambda) $。</span><span class="sxs-lookup"><span data-stu-id="ec2db-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>