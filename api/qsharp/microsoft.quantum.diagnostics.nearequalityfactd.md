---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698059"
---
# <a name="nearequalityfactd-function"></a>NearEqualityFactD 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


判斷值，傳統浮點值的預期值最高可達 1e-10 的小容錯。

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--double"></a>實際： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

要檢查的數位。


### <a name="expected--double"></a>預期： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

預期的值。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

這相當於 <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> 具有 $10 ^ $ 的硬式編碼容錯 {-10} 。