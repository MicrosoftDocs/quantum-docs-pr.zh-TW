---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698067"
---
# <a name="formattedfailure-function"></a>FormattedFailure 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


內建函式用來因有意義的錯誤訊息而失敗。

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--t"></a>實際： t




### <a name="expected--t"></a>預期： t




### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="remarks"></a>備註

此函式的目的是要由模擬執行時間模擬，以便允許轉送格式化您一致。