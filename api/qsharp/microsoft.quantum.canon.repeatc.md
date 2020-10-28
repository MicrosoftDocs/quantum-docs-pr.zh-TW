---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 8dc178374bdc9f8bf9f8aed57b9ae9a56995dec6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698890"
---
# <a name="repeatc-operation"></a>RepeatC 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


以指定的次數重複作業。

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>輸入

### <a name="op--tinput--unit-ctl"></a>op： ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

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
- [Canon. 重複](xref:Microsoft.Quantum.Canon.Repeat)
- [Canon. RepeatA](xref:Microsoft.Quantum.Canon.RepeatA)
- [Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)