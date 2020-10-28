---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698087"
---
# <a name="equalitywithintolerancefact-function"></a>EqualityWithinToleranceFact 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


表示傳統浮點數值的預期值為指定絕對容錯值的宣告。

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--double"></a>實際： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

要檢查的數位。


### <a name="expected--double"></a>預期： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

預期的值。


### <a name="tolerance--double"></a>容錯： [Double](xref:microsoft.quantum.lang-ref.double)

實際和預期之間差異的絕對容錯。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

