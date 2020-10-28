---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698098"
---
# <a name="equalityfactc-function"></a>EqualityFactC 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


判斷複數具有預期的值。

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--complex"></a>實際： [複雜](xref:Microsoft.Quantum.Math.Complex)

要檢查的值。


### <a name="expected--complex"></a>預期： [複雜](xref:Microsoft.Quantum.Math.Complex)

預期的值。


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

觸發判斷提示時要使用的失敗訊息字串。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

