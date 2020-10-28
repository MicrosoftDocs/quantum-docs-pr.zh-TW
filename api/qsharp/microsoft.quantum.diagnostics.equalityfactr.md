---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698086"
---
# <a name="equalityfactr-function"></a>EqualityFactR 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


判斷提示傳統結果變數具有預期的值。

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--__invalidresult__"></a>實際： __無效 <Result>__

要檢查的變數。


### <a name="expected--__invalidresult__"></a>預期： __無效 <Result>__

預期的值。


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

觸發判斷提示時要使用的失敗訊息字串。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

