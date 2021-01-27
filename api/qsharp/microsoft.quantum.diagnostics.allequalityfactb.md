---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 725291e8b5d12683ad580d5938dadd561831e88e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853548"
---
# <a name="allequalityfactb-function"></a>AllEqualityFactB 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

