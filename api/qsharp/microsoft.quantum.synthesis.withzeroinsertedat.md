---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 6e13251741dadb19740b208cdfc13a14964a48dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701047"
---
# <a name="withzeroinsertedat-function"></a>WithZeroInsertedAt 函式

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

包： [](https://nuget.org/packages/)


將0位插入整數

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>描述

這種作業會接受整數、插入0位 `position` ，然後以整數傳回更新的值。  例如，在數位 10 ($10 _ = 1010_ $) 的位置2插入0會傳回 {10} {2} 數位 18 ($18 _ {10} = 10010_ {2} $) 。

## <a name="input"></a>輸入

### <a name="position--int"></a>position： [Int](xref:microsoft.quantum.lang-ref.int)

插入0的位置


### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

修改過的值



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

修改過的值