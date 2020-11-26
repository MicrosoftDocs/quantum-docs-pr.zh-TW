---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimateOverlapBetweenStates 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 07693ccf4b8e7bbde189674d9e6b2bf7f92222f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204295"
---
# <a name="estimateoverlapbetweenstates-operation"></a>EstimateOverlapBetweenStates 操作

命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


假設有兩個作業，每個作業都會準備狀態的複本，並估計每個作業所準備的狀態之間的平方重迭。

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>輸入

### <a name="preparation1--qubit--unit--is-adj"></a>preparation1： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

要比較的兩個狀態準備作業中的第一個。


### <a name="preparation2--qubit--unit--is-adj"></a>preparation2： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

要比較的兩個狀態準備作業的第二個。


### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

`commonPreparation`、 `preparation1` 和所有 act 的量子位數目 `preparation2` 。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

用來估計重迭的度量數目。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>備註

這種操作會使用交換測試來尋找 $ $ \begin{align} \left |\braket{00\cdots 0 |V ^ {\dagger} U |00 \ cdots 0} \right | ^ 2 \end{align} $ $，其中 $U $ 是的動作的單一標記法 `preparation1` ，以及 $V $ 對應的位置 `preparation2` 。

## <a name="see-also"></a>另請參閱

- [EstimateRealOverlapBetweenStates。](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [EstimateImagOverlapBetweenStates。](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)