---
uid: Microsoft.Quantum.Convert.Call
title: 呼叫作業
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850200"
---
# <a name="call-operation"></a>呼叫作業

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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