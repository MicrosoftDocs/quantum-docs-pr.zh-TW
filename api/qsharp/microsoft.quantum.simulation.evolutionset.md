---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 41504837b281b1021a2d09ef75acc10315b4fd07
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697478"
---
# <a name="evolutionset-user-defined-type"></a>EvolutionSet 使用者定義型別

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


代表一組可用來實作為模擬演算法的閘道。

集合中的專案是由所編制索引  <xref:microsoft.quantum.simulation.generatorindex> ，而且每個集合都是由的函式描述 `GeneratorIndex` ，而  <xref:microsoft.quantum.simulation.evolutionunitary> 這是由代表時間的實數所參數化的作業。

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```
