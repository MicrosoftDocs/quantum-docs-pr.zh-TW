---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliGenIdx
title: _ZZTermToPauliGenIdx 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 01f4ebf4f2acc0fd76ae101e0c511cd70b03fada
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214954"
---
# <a name="_zztermtopauligenidx-function"></a>_ZZTermToPauliGenIdx 函式

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


在 Paulis 方面，將描述 ZZ 詞彙的 GeneratorIndex 轉換為運算式 ' GeneratorIndex [] '。

```qsharp
function _ZZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a>輸入

### <a name="term--generatorindex"></a>詞彙： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` 代表 ZZ 詞彙。



## <a name="output--generatorindex"></a>輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]

將 ZZ 詞彙表示為 Pauli 詞彙的 ' GeneratorIndex [] '。