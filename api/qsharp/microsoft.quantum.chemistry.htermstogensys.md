---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204108"
---
# <a name="htermstogensys-function"></a>HTermsToGenSys 函式

命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


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