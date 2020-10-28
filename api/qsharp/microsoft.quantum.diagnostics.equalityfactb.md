---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698095"
---
# <a name="equalityfactb-function"></a>EqualityFactB 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


判斷提示傳統 Bool 變數具有預期的值。

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--bool"></a>實際： [Bool](xref:microsoft.quantum.lang-ref.bool)

要檢查的變數。


### <a name="expected--bool"></a>預期： [Bool](xref:microsoft.quantum.lang-ref.bool)

預期的值。


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

觸發判斷提示時要使用的失敗訊息字串。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

