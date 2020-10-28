---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerBlockEncodingGeneratorSystem
title: JordanWignerBlockEncodingGeneratorSystem 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: 68693465aeb030abbc514dacb789c234901fe120
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698479"
---
# <a name="jordanwignerblockencodinggeneratorsystem-function"></a>JordanWignerBlockEncodingGeneratorSystem 函式

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

包： [](https://nuget.org/packages/)


將描述的 Hamiltonian 轉換 `JWOptimizedHTerms` 成以 `GeneratorSystem` Pauli 表示的 `GeneratorIndex` 。

```qsharp
function JordanWignerBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>輸入

### <a name="data--jwoptimizedhterms"></a>資料： [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)

格式的 Hamiltonian 描述 `JWOptimizedHTerms` 。



## <a name="output--generatorsystem"></a>輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Hamiltonian 的標記法 `GeneratorSystem` 。