---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSingleConfigurationalStateSingleSiteOccupation
title: PrepareSingleConfigurationalStateSingleSiteOccupation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSingleConfigurationalStateSingleSiteOccupation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: de385b7ffd76c1deaa41cf0cd3338d3243feb1fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698407"
---
# <a name="preparesingleconfigurationalstatesinglesiteoccupation-operation"></a>PrepareSingleConfigurationalStateSingleSiteOccupation 操作

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

包： [](https://nuget.org/packages/)


藉由佔用微調 orbitals，來準備試用狀態的簡單狀態

```qsharp
operation PrepareSingleConfigurationalStateSingleSiteOccupation (qubitIndices : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="qubitindices--int"></a>qubitIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]

電子要佔用的量子位索引。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

Hamiltonian 的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

