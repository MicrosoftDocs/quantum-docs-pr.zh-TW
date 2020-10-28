---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700847"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="cdcee-102">TruthTablesFromPermutationFolder 函式</span><span class="sxs-lookup"><span data-stu-id="cdcee-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="cdcee-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="cdcee-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="cdcee-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cdcee-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cdcee-105">單一變數索引的分解邏輯</span><span class="sxs-lookup"><span data-stu-id="cdcee-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="cdcee-106">描述</span><span class="sxs-lookup"><span data-stu-id="cdcee-106">Description</span></span>

<span data-ttu-id="cdcee-107">這會取得目前的狀態，並產生更新的排列，而且可能會為控制的閘道加入新的功能。</span><span class="sxs-lookup"><span data-stu-id="cdcee-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="cdcee-108">輸入</span><span class="sxs-lookup"><span data-stu-id="cdcee-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="cdcee-109">numVars： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cdcee-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="cdcee-110">狀態： [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="cdcee-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="cdcee-111">index： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cdcee-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="cdcee-112">輸出： [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="cdcee-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

