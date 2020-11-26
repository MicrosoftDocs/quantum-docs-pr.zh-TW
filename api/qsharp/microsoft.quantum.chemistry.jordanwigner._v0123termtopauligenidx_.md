---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: fc5ad0e97374c52a90012b0ce633af8488f3ad88
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215090"
---
# <a name="_v0123termtopauligenidx_-function"></a>_V0123TermToPauliGenIdx_ 函式

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


根據 Paulis 將描述 PQRS 詞彙的 GeneratorIndex 轉換為運算式 ' GeneratorIndex [] '

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a>輸入

### <a name="term--generatorindex"></a>詞彙： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` 代表 PQRS 字詞。



## <a name="output--generatorindex"></a>輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]

將 PQRS 詞彙表示為 Pauli 詞彙的 ' GeneratorIndex [] '。