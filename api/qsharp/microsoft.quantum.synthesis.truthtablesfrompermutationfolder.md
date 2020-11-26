---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 86e112782825303805029b2f9f6cfd9d6ce9e8b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231019"
---
# <a name="truthtablesfrompermutationfolder-function"></a>TruthTablesFromPermutationFolder 函式

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


單一變數索引的分解邏輯

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a>描述

這會取得目前的狀態，並產生更新的排列，而且可能會為控制的閘道加入新的功能。

## <a name="input"></a>輸入

### <a name="numvars--int"></a>numVars： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="state--decompositionstate"></a>狀態： [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)




### <a name="index--int"></a>index： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--decompositionstate"></a>輸出： [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)

