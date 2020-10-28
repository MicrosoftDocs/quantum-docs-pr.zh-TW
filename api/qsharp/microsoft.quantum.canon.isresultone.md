---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: fa8845fd92e5c16b4ff15436caf42df4f1e151cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699003"
---
# <a name="isresultone-function"></a>IsResultOne 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


測試給定的結果值是否等於 `One` 。

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a>輸入

### <a name="input--__invalidresult__"></a>輸入： __無效 <Result>__

`Result` 要測試的值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true`如果 `input` 等於，則會傳回 `One` 。