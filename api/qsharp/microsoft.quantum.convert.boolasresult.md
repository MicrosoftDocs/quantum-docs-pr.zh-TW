---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 0190529dd804922a69499fbf1c2c4c916c4b720a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214240"
---
# <a name="boolasresult-function"></a>BoolAsResult 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將型別轉換為 `Bool` `Result` 型別，其中 `true` 對應至， `One` 而且 `false` 會對應至 `Zero` 。

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a>輸入

### <a name="input--bool"></a>輸入： [Bool](xref:microsoft.quantum.lang-ref.bool)

`Bool` 要轉換的。



## <a name="output--__invalidresult__"></a>輸出：__無效 <Result>__

`Result`，代表 `input`。