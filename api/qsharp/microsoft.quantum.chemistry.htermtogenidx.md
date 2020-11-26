---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 59391a882fdbc55172ee93a7428c1735bbb29500
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216025"
---
# <a name="htermtogenidx-function"></a>HTermToGenIdx 函式

命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


將資料格式的 Hamiltonian 詞彙轉換 `HTerm` 成 GeneratorIndex。

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>輸入

### <a name="term--hterm"></a>詞彙： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)

以格式輸入資料 `HTerm` 。


### <a name="termtype--int"></a>termType： [Int](xref:microsoft.quantum.lang-ref.int)[]

新增至 GeneratorIndex 的其他資訊。



## <a name="output--generatorindex"></a>輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

代表所表示之 Hamiltonian 詞彙的 GeneratorIndex `term` ，以及新增的其他資訊 `termType` 。