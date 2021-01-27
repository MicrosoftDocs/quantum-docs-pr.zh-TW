---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 7b7a4fea8973727da4dcab6f739c6db8da835a2f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843437"
---
# <a name="assertphaselessthan-operation"></a>AssertPhaseLessThan 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


判斷提示 `number` 中編碼的 PhaseLittleEndian 小於 `value` 。

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

`number` 必須小於這個。


### <a name="number--phaselittleendian"></a>編號： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

與比較的不帶正負號的整數 `value` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

此操作的受控制版本會忽略控制項。