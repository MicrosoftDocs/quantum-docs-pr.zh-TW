---
uid: Microsoft.Quantum.Canon.Repeat
title: 重複操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 40ee191e8d9044f33aa1621303c70f7e0847e8f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852235"
---
# <a name="repeat-operation"></a>重複操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>範例

以下是相等的：

```qsharp
Repeat(U, 17, target);
(Bound(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a>另請參閱

- [DrawMany。](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Canon. RepeatA](xref:Microsoft.Quantum.Canon.RepeatA)
- [Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)
- [Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)