---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227772"
---
# <a name="modulusi-function"></a>ModulusI 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


計算模數的標準 residue `value` `modulus` 。

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a>輸入

### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

計算 residue 的值


### <a name="modulus--int"></a>模數： [Int](xref:microsoft.quantum.lang-ref.int)

Residues 所採用的模數必須是正數



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

0之間的整數 $r $，因此 `modulus - 1` `value - r` 模數可以整除

## <a name="remarks"></a>備註

此函式的行為與運算子 `%` 在 c # 和 Q # 中的運作方式不同，因為結果中的結果一律是0和之間的正整數 `modulus - 1` ，即使值為負數。