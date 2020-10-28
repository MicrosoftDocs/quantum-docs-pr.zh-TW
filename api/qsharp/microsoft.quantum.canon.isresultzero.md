---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: 790551690cfba42df4cf7aa77e53e303050bdf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699000"
---
# <a name="isresultzero-function"></a>IsResultZero 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


測試給定的結果值是否等於 `Zero` 。

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a>輸入

### <a name="input--__invalidresult__"></a>輸入： __無效 <Result>__

`Result` 要測試的值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true`如果 `input` 等於，則會傳回 `Zero` 。