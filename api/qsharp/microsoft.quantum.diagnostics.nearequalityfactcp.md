---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 477449913732950ad26adc0cdabaaaab803a20c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853274"
---
# <a name="nearequalityfactcp-function"></a>NearEqualityFactCP 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


判斷值，傳統複數的預期值最高可達 1e-10 的小容錯。

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--complexpolar"></a>實際： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

要檢查的數位。


### <a name="expected--complexpolar"></a>預期： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

預期的值。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

