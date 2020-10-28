---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701138"
---
# <a name="sizeadjustedtruthtable-function"></a>SizeAdjustedTruthTable 函式

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

包： [](https://nuget.org/packages/)


根據變數數目，從布林值陣列調整事實資料表

會傳回長度為的新陣列 `2^numVars` ，可能需要以 `table` 專案擴充大小， `false` 或將它截斷為 `2^numVars` 元素。

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>輸入

### <a name="table--bool"></a>table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

事實資料表作為真實值的陣列


### <a name="numvars--int"></a>numVars： [Int](xref:microsoft.quantum.lang-ref.int)

變數數目



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

調整真大小的事實資料表