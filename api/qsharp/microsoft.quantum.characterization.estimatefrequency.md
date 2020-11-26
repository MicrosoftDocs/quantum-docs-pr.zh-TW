---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 30b21a8e86eb5a4dd8dd8207dbdc6a0970308319
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216246"
---
# <a name="estimatefrequency-operation"></a>EstimateFrequency 操作

命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在準備和測量之後，請透過 `Zero` 執行指定的試用次數，估計 (傳回) 的測量頻率。

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>輸入

### <a name="preparation--qubit--unit"></a>準備： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 

作業 $P $，在其輸入暫存器上準備指定的狀態 $ \rho $。


### <a name="measurement--qubit--__invalidresult__"></a>測量：[量子位](xref:microsoft.quantum.lang-ref.qubit)[] =>__無效 <Result>__ 

作業 $M $ 代表感興趣的度量。


### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

每個動作的準備和測量量子位數目。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

應執行測量的次數，以估計感興趣的頻率。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

$M (P ( \ket{00 \cdots 0} \bra{00 \cdots 0} ) # B3 $ 傳回的估計 $ \hat{p} $ `Zero` ，其使用非偏誤二項式估算器 $ \hat{p} = n \_ {\uparrow}/n \_ {\text{measurements}} $ 來取得，其中 $n \_ {\uparrow} $ 是 `Zero` 觀察到的結果數目。

這對具有實體限制的目的電腦特別重要，因為無法測量機率。