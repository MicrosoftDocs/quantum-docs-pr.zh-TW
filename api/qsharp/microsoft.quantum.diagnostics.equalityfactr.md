---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 86d2ddff79f0bca7badd95a2fe2156c558fa7f86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853339"
---
# <a name="equalityfactr-function"></a>EqualityFactR 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


判斷提示傳統結果變數具有預期的值。

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--__invalidresult__"></a>實際：__無效 <Result>__

要檢查的變數。


### <a name="expected--__invalidresult__"></a>預期：__無效 <Result>__

預期的值。


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

觸發判斷提示時要使用的失敗訊息字串。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

