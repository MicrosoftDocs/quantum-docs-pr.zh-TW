---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: dbe0718fa3b5439a2987d455fdad73731c988678
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216008"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx 函式

命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


將資料格式的 Hamiltonian 詞彙轉換成 `HTerm[]` GeneratorIndex。

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>輸入

### <a name="data--hterm"></a>data： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

以格式輸入資料 `HTerm[]` 。


### <a name="termtype--int"></a>termType： [Int](xref:microsoft.quantum.lang-ref.int)[]

新增至 GeneratorIndex 的其他資訊。


### <a name="idx--int"></a>idx： [Int](xref:microsoft.quantum.lang-ref.int)

Hamiltonian 詞彙的索引



## <a name="output--generatorindex"></a>輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

代表所表示之 Hamiltonian 詞彙的 GeneratorIndex `data[idx]` ，以及新增的其他資訊 `termType` 。