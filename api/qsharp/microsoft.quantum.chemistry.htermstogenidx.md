---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698690"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx 函式

命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)

包： [](https://nuget.org/packages/)


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