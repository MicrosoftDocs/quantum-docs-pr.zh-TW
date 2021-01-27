---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843415"
---
# <a name="assertmostsignificantbit-operation"></a>AssertMostSignificantBit 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


判斷提示代表不帶正負號的整數之量子位暫存器最重要的量子位處於特定狀態。

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="value--__invalidresult__"></a>值：__無效 <Result>__

要判斷提示的最高位值。


### <a name="number--littleendian"></a>編號： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

檢查最大位的不帶正負號的整數。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

此操作的受控制版本會忽略控制項。

## <a name="see-also"></a>另請參閱

- [... Assert](xref:Microsoft.Quantum.Intrinsic.Assert)