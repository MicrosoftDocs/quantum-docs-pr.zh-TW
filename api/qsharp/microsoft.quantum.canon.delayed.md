---
uid: Microsoft.Quantum.Canon.Delayed
title: 延遲函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699032"
---
# <a name="delayed-function"></a>延遲函數

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


傳回以指定的引數套用指定作業的作業。

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a>輸入

### <a name="op--t--u"></a>op： t => ' U 

要套用的作業。


### <a name="arg--t"></a>arg： t

要套用作業的輸入。



## <a name="output--unit--u"></a>Output： [Unit](xref:microsoft.quantum.lang-ref.unit) => ' U 

適用于輸入的新作業 `op``arg`

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要延遲之作業的輸入類型。
### <a name="u"></a>' U

要延遲之作業的傳回型別。

## <a name="see-also"></a>另請參閱

- [Canon. DelayedC](xref:Microsoft.Quantum.Canon.DelayedC)
- [Canon. DelayedA](xref:Microsoft.Quantum.Canon.DelayedA)
- [Canon. DelayedCA](xref:Microsoft.Quantum.Canon.DelayedCA)
- [Canon. 延遲](xref:Microsoft.Quantum.Canon.Delay)