---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834199"
---
# <a name="boolarrayasresultarray-function"></a>BoolArrayAsResultArray 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將型別轉換為 `Bool[]` `Result[]` 型別，其中 `true` 對應至， `One` 而且 `false` 會對應至 `Zero` 。

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a>輸入

### <a name="input--bool"></a>輸入： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` 要轉換的。



## <a name="output--__invalidresult__"></a>輸出：__無效 <Result>__ 的 []

`Result[]`，代表 `input`。