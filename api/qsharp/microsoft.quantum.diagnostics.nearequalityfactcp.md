---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 1d62d25a3d04c431440cf8fc1eb585cac2c73f2e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698062"
---
# <a name="nearequalityfactcp-function"></a>NearEqualityFactCP 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


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

