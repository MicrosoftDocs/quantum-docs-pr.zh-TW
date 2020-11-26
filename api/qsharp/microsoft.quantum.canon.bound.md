---
uid: Microsoft.Quantum.Canon.Bound
title: 綁定函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: c12ce37054ddde1b98778888e90916c6e4725814
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207593"
---
# <a name="bound-function"></a>綁定函數

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a>輸入

### <a name="operations--t--unit-"></a>作業： t => [單位](xref:microsoft.quantum.lang-ref.unit) []

要在指定的輸入上執行的一連串作業。



## <a name="output--t--unit"></a>輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit) 

在其輸入上依序執行每個指定作業的新作業。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

陣列中的每個作業所作用的目標。

## <a name="see-also"></a>另請參閱

- [Canon. BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Canon. BoundA](xref:Microsoft.Quantum.Canon.BoundA)
- [Canon. BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)