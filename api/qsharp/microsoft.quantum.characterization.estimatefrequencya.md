---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: EstimateFrequencyA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 88f0a237975c158bffcc015f79d2134b210ce83b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698750"
---
# <a name="estimatefrequencya-operation"></a>EstimateFrequencyA 操作

命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)

包： [](https://nuget.org/packages/)


針對 adjointable 和測量的準備工作，會透過 `Zero` 執行指定的試用次數，估計 (傳回) 的測量頻率。

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>輸入

### <a name="preparation--qubit--unit-adj"></a>準備： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

Adjointable 作業 $P $，在其輸入暫存器上準備指定的狀態 $ \rho $。


### <a name="measurement--qubit--__invalidresult__"></a>測量： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => __無效 <Result>__ 

作業 $M $ 代表感興趣的度量。


### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

每個動作的準備和測量量子位數目。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

應執行測量的次數，以估計感興趣的頻率。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

$M (P ( \ket{00 \cdots 0} \bra{00 \cdots 0} ) # B3 $ 傳回的估計 $ \hat{p} $ `Zero` ，其使用非偏誤二項式估算器 $ \hat{p} = n \_ {\uparrow}/n \_ {\text{measurements}} $ 來取得，其中 $n \_ {\uparrow} $ 是 `Zero` 觀察到的結果數目。

## <a name="remarks"></a>備註

針對 adjointable 作業，可以進行某些假設，例如呼叫作業會將量子位準備成完全相同的狀態，如此可讓目的電腦進行一些效能優化。