---
uid: Microsoft.Quantum.Convert.Call
title: 呼叫作業
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698311"
---
# <a name="call-operation"></a>呼叫作業

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

包： [](https://nuget.org/packages/)


使用指定的輸入呼叫函數。

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>描述

假設函式和該函式的輸入，則會呼叫函式並傳回其輸出。

## <a name="input"></a>輸入

### <a name="fn--input---output"></a>fn： ' Input-> ' 輸出

要呼叫的函式。


### <a name="input--input"></a>輸入： ' Input

要傳遞至函數的輸入。



## <a name="output--output"></a>輸出： ' Output

呼叫 `fn` 的結果。

## <a name="type-parameters"></a>類型參數

### <a name="input"></a>' 輸入


### <a name="output"></a>' 輸出



## <a name="remarks"></a>備註

這項作業主要適合用來強制在作業內的特定位置呼叫函式，或在需要作業的情況下呼叫函數。