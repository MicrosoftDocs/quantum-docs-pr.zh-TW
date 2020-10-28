---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698179"
---
# <a name="allequalityfacti-function"></a>AllEqualityFactI 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


判斷提示兩個整數值陣列是否相等。

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--int"></a>實際： [Int](xref:microsoft.quantum.lang-ref.int)[]

由感興趣的測試案例所產生的陣列。


### <a name="expected--int"></a>預期： [Int](xref:microsoft.quantum.lang-ref.int)[]

預期來自感興趣之測試案例的陣列。


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

如果陣列不相等，則為要列印的訊息。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

