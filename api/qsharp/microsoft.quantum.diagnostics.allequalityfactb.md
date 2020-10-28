---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698182"
---
# <a name="allequalityfactb-function"></a>AllEqualityFactB 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


判斷提示兩個布林值陣列是否相等。

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--bool"></a>實際： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

由感興趣的測試案例所產生的陣列。


### <a name="expected--bool"></a>預期： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

預期來自感興趣之測試案例的陣列。


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

如果陣列不相等，則為要列印的訊息。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

