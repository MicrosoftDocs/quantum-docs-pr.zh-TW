---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: EstimateRealOverlapBetweenStates 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 01631bcbff2bff26ddc1db4e42d90ac4f8380bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698723"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a>EstimateRealOverlapBetweenStates 操作

命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)

包： [](https://nuget.org/packages/)


假設有兩個作業，每個作業都會準備狀態的複本，並估計每個作業所準備的狀態之間重迭的實際部分。

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>輸入

### <a name="commonpreparation--qubit--unit-adj"></a>commonPreparation： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

準備固定輸入狀態的作業。


### <a name="preparation1--qubit--unit-adj--ctl"></a>preparation1： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

要比較的兩個狀態準備作業中的第一個。


### <a name="preparation2--qubit--unit-adj--ctl"></a>preparation2： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

要比較的兩個狀態準備作業的第二個。


### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

`commonPreparation`、 `preparation1` 和所有 act 的量子位數目 `preparation2` 。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

用來估計重迭的度量數目。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>備註

這項作業會使用 Hadamard 測試來尋找 $ $ \begin{align} \braket{\psi 的真實部分 |V ^ {\dagger} U |\psi} \end{align} $ $，其中 $ \ket{\psi} $ 是所準備的狀態 `commonPreparation` ，$U $ 是的動作的單一標記法 `preparation1` ，以及 $V $ 對應至的位置 `preparation2` 。

## <a name="references"></a>參考

- Aharonov *et al.exe.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096)。

## <a name="see-also"></a>另請參閱

- [EstimateImagOverlapBetweenStates。](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [EstimateOverlapBetweenStates。](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)