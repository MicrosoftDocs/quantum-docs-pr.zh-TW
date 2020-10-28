---
uid: Microsoft.Quantum.Canon.Repeat
title: 重複操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5aedd056b851b8d8d7c25a32eb22587292e132a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698902"
---
# <a name="repeat-operation"></a>重複操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


以指定的次數重複作業。

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>輸入

### <a name="op--tinput--unit"></a>op： ' TInput => [單位](xref:microsoft.quantum.lang-ref.unit) 

要重複呼叫的作業。


### <a name="ntimes--int"></a>nTimes： [Int](xref:microsoft.quantum.lang-ref.int)

要呼叫的次數 `op` 。


### <a name="input--tinput"></a>輸入： ' TInput

要傳遞至的輸入 `op` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="tinput"></a>'TInput



## <a name="see-also"></a>另請參閱

- [DrawMany。](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Canon. RepeatA](xref:Microsoft.Quantum.Canon.RepeatA)
- [Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)
- [Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)