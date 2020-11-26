---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224372"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將函數轉換成作業。

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>描述

指定函式時，會傳回呼叫該函式，而不會執行其他動作的作業。

## <a name="input"></a>輸入

### <a name="fn--input---output"></a>fn： ' Input-> ' 輸出

要轉換成運算的函式。



## <a name="output--input--output"></a>輸出： ' Input => ' 輸出 

與 `op` `op(input)` 全部相同的作業 `fn(input)` `input` 。

## <a name="type-parameters"></a>類型參數

### <a name="input"></a>' 輸入

要轉換之函數的輸入類型。
### <a name="output"></a>' 輸出

要轉換之函數的輸出類型。

## <a name="remarks"></a>備註

這項功能主要適用于將函式傳遞至預期作業為輸入的函式或作業。