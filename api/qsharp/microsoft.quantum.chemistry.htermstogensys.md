---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: b78ff393fa1e51c38028ef56bb3c61b8f1d5e478
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698686"
---
# <a name="htermstogensys-function"></a>HTermsToGenSys 函式

命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)

包： [](https://nuget.org/packages/)


將資料格式的 Hamiltonian 轉換 `HTerm[]` 為 GeneratorSystem。

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>輸入

### <a name="data--hterm"></a>data： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

以格式輸入資料 `HTerm[]` 。


### <a name="termtype--int"></a>termType： [Int](xref:microsoft.quantum.lang-ref.int)[]

新增至 GeneratorIndex 的其他資訊。



## <a name="output--generatorsystem"></a>輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

代表輸入所代表之 Hamiltonian 的 GeneratorSystem `data` 。