---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699080"
---
# <a name="ccontrolled-function"></a>CControlled 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


在指定作業作業的情況下，會傳回新的作業，如果傳統的控制項位為 true，就會套用 op。 如果為，則不 `false` 會發生任何事。

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a>輸入

### <a name="op--t--unit"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 

有條件地套用的作業。



## <a name="output--boolt--unit"></a>Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，t) => [單位](xref:microsoft.quantum.lang-ref.unit) 

如果傳統控制位為 true，則為 op 的新作業。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要有條件地套用之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. CControlledC](xref:Microsoft.Quantum.Canon.CControlledC)
- [Canon. CControlledA](xref:Microsoft.Quantum.Canon.CControlledA)
- [Canon. CControlledCA](xref:Microsoft.Quantum.Canon.CControlledCA)