---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 89d34e5a30a61dee392904ce1076605432e21395
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698891"
---
# <a name="repeata-operation"></a>RepeatA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


以指定的次數重複作業。

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>輸入

### <a name="op--tinput--unit-adj"></a>op： ' TInput => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

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
- [Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)
- [Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)