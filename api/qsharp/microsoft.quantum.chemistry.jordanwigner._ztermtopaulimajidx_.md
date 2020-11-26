---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliMajIdx_
title: _ZTermToPauliMajIdx_ 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 13897d831bc3382dbb23b653c5905978330eb622
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214988"
---
# <a name="_ztermtopaulimajidx_-function"></a>_ZTermToPauliMajIdx_ 函式

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


在 Paulis 方面，將描述 Z 詞彙的 GeneratorIndex 轉換為運算式 ' GeneratorIndex [] '。

```qsharp
function _ZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a>輸入

### <a name="term--generatorindex"></a>詞彙： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` 代表 Z 詞彙。



## <a name="output--optimizedbetermindex"></a>輸出： [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)

將 Z 詞彙表示為 Pauli 詞彙的 ' GeneratorIndex [] '。