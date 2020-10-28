---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699505"
---
# <a name="drawmany-operation"></a>DrawMany 操作

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


針對指定的樣本數重複作業，並在陣列中收集其輸出。

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>輸入

### <a name="op--tinput--toutput"></a>op： ' TInput => ' Toutput> 

要重複呼叫的作業。


### <a name="nsamples--int"></a>nSamples： [Int](xref:microsoft.quantum.lang-ref.int)

要收集的呼叫樣本數 `op` 。


### <a name="input--tinput"></a>輸入： ' TInput

要傳遞至的輸入 `op` 。



## <a name="output--toutput"></a>輸出： ' Toutput> []



## <a name="type-parameters"></a>類型參數

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>' Toutput>



## <a name="see-also"></a>另請參閱

- [Canon. 重複](xref:Microsoft.Quantum.Canon.Repeat)