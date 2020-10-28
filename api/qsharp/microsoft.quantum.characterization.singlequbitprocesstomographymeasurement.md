---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 34e5143d5be316ee42a63124d35475949db0a692
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698710"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a>SingleQubitProcessTomographyMeasurement 操作

命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)

包： [](https://nuget.org/packages/)


指定特定的通道，以 Pauli 為基礎執行單一量子位流程 tomography 測量。

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a>輸入

### <a name="preparation--pauli"></a>準備： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

要準備量子位的 Pauli 基礎元素 $P $。


### <a name="measurement--pauli"></a>測量： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

要測量量子位的 Pauli 基礎元素 $Q $。


### <a name="channel--qubit--unit"></a>通道： [量子位](xref:microsoft.quantum.lang-ref.qubit) => [單位](xref:microsoft.quantum.lang-ref.unit) 

單一量子位通道 $ \Lambda $，其行為正以進程 tomography 進行評估。



## <a name="output--__invalidresult__"></a>輸出： __無效 <Result>__

`Zero`Probability $ $ \Begin{align} \Pr ( \texttt{zero} | \Lambda; 的結果P，Q) = \operatorname{Tr}\left ( \frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right) 。
\end{align} $ $

## <a name="remarks"></a>備註

這項作業所傳回之結果的散發是雙量子位狀態 tomography 的特殊案例。 Let $ \rho = J ( \Lambda) /$2 是 $ \Lambda $ 的 Choi 對於– Jamiłkowski 狀態。 然後，上述散發與 $ $ \begin{align} \Pr ( \texttt{Zero} 相同。rhoM) = \operatorname{Tr} (M \rho) ，\end{align} $ $ where $M = 2 ( \boldone + P) ^ \mathrm{T}/2 \cdot ( \boldone + Q) /$2 是對應至 $P $ 和 $Q $ 的有效測量。