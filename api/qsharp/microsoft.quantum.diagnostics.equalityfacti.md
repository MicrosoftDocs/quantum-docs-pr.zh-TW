---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: c41cb5548e8dfebb4d1c1a1c052306878c85e821
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853341"
---
# <a name="equalityfacti-function"></a>EqualityFactI 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


判斷提示傳統 Int 變數具有預期的值。

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--int"></a>實際： [Int](xref:microsoft.quantum.lang-ref.int)

要檢查的數位。


### <a name="expected--int"></a>預期： [Int](xref:microsoft.quantum.lang-ref.int)

預期的值。


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

觸發判斷提示時要使用的失敗訊息字串。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

