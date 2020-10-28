---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 50a2bdb4a73ef9d67d3f5532493c142bb7f753cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698330"
---
# <a name="boolarrayasresultarray-function"></a>BoolArrayAsResultArray 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

包： [](https://nuget.org/packages/)


將型別轉換為 `Bool[]` `Result[]` 型別，其中 `true` 對應至， `One` 而且 `false` 會對應至 `Zero` 。

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a>輸入

### <a name="input--bool"></a>輸入： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` 要轉換的。



## <a name="output--__invalidresult__"></a>輸出： __無效 <Result>__ 的 []

`Result[]`，代表 `input`。