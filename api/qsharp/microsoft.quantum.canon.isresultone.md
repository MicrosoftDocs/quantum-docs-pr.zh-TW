---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: eb4116b60bb415465375e374ad84e990135c231c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206539"
---
# <a name="isresultone-function"></a>IsResultOne 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


測試給定的結果值是否等於 `One` 。

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a>輸入

### <a name="input--__invalidresult__"></a>輸入：__無效 <Result>__

`Result` 要測試的值。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true`如果 `input` 等於，則會傳回 `One` 。