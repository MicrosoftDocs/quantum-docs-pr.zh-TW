---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 9de7ca64992e0a4d73c1d00218b3eab4ab545a1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832551"
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