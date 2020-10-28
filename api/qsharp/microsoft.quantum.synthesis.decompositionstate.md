---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: DecompositionState 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701063"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="ddaf5-102">DecompositionState 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="ddaf5-102">DecompositionState user defined type</span></span>

<span data-ttu-id="ddaf5-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ddaf5-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ddaf5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ddaf5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ddaf5-105">根據變數索引進行分解時的狀態</span><span class="sxs-lookup"><span data-stu-id="ddaf5-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="ddaf5-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="ddaf5-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="ddaf5-107">為永久： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ddaf5-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="ddaf5-108">Lfunctions： ([BigInt](xref:microsoft.quantum.lang-ref.bigint)，[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="ddaf5-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="ddaf5-109">Rfunctions： ([BigInt](xref:microsoft.quantum.lang-ref.bigint)，[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="ddaf5-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="ddaf5-110">描述</span><span class="sxs-lookup"><span data-stu-id="ddaf5-110">Description</span></span>

<span data-ttu-id="ddaf5-111">狀態會保留目前的排列，以及左側控制的閘道目前產生的函式，以及右邊的控制管制。</span><span class="sxs-lookup"><span data-stu-id="ddaf5-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>