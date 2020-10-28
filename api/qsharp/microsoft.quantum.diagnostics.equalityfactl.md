---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698090"
---
# <a name="equalityfactl-function"></a>EqualityFactL 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


判斷提示傳統 BigInt 變數具有預期的值。

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--bigint"></a>實際： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要檢查的數位。


### <a name="expected--bigint"></a>預期： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

預期的值。


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

觸發判斷提示時要使用的失敗訊息字串。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

