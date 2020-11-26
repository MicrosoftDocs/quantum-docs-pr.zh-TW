---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerClusterOperatorGeneratorSystem
title: JordanWignerClusterOperatorGeneratorSystem 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerClusterOperatorGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: e6deca3c8261c7730e9b208d9f834ad0db101fd3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214801"
---
# <a name="jordanwignerclusteroperatorgeneratorsystem-function"></a>JordanWignerClusterOperatorGeneratorSystem 函式

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


將描述的 Hamiltonian 轉換為，以這個檔案中 `JWOptimizedHTerms` `GeneratorSystem` 定義的 `GeneratorIndex` 慣例表示。

```qsharp
function JordanWignerClusterOperatorGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>輸入

### <a name="data--jordanwignerinputstate"></a>data： [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]

格式的 Hamiltonian 描述 `JWOptimizedHTerms` 。



## <a name="output--generatorsystem"></a>輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Hamiltonian 的標記法 `GeneratorSystem` 。