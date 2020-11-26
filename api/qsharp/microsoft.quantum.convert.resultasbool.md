---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: a170acf635e4e2b2150ffc208fabc9782ff837b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224168"
---
# <a name="resultasbool-function"></a>ResultAsBool 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將型別轉換為 `Result` `Bool` 型別，其中 `One` 對應至， `true` 而且 `Zero` 會對應至 `false` 。

```qsharp
function ResultAsBool (input : Result) : Bool
```


## <a name="input"></a>輸入

### <a name="input--__invalidresult__"></a>輸入：__無效 <Result>__

`Result` 要轉換的。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`，代表 `input`。