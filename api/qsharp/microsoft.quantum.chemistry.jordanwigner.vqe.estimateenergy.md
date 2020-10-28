---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: EstimateEnergy 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: 52e527a68818c80f93bc177d3563064fd0f2aea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698374"
---
# <a name="estimateenergy-operation"></a>EstimateEnergy 操作

命名空間： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

包： [](https://nuget.org/packages/)


藉由將個別 Jordan-Wigner 詞彙所貢獻的能源加總，來估計分子的能源。

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a>描述

這種作業隱含依賴微調索引慣例。

## <a name="input"></a>輸入

### <a name="jwhamiltonian--jordanwignerencodingdata"></a>jwHamiltonian： [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Jordan-Wigner Hamiltonian。


### <a name="nsamples--int"></a>nSamples： [Int](xref:microsoft.quantum.lang-ref.int)

要用於估計字詞預期的樣本數。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

預估的分子能源