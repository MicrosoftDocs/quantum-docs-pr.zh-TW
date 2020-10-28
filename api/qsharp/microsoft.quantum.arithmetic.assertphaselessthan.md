---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699951"
---
# <a name="assertphaselessthan-operation"></a>AssertPhaseLessThan 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


判斷提示 `number` 中編碼的 PhaseLittleEndian 小於 `value` 。

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a>輸入

### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

`number` 必須小於這個。


### <a name="number--phaselittleendian"></a>編號： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

與比較的不帶正負號的整數 `value` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

此操作的受控制版本會忽略控制項。