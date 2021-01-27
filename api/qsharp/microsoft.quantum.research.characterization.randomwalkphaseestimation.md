---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: RandomWalkPhaseEstimation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: f9edafcce62c8b30a6bd52b7dbaa2df2c50c920d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846009"
---
# <a name="randomwalkphaseestimation-operation"></a>RandomWalkPhaseEstimation 操作

命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Characterization) ..........。

封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization) ...........。


使用隨機的逐步解說，在給定 oracle 和 eigenstate 的傳統測量結果上，使用近似的貝氏推斷，執行反復的階段估計。

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>輸入

### <a name="initialmean--double"></a>initialMean： [Double](xref:microsoft.quantum.lang-ref.double)

初始一般之前分佈于 $ \phi $ 的平均值。


### <a name="initialstddev--double"></a>initialStdDev： [Double](xref:microsoft.quantum.lang-ref.double)

初始一般之前分佈于 $ \phi $ 的標準差。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

要在最終「事後 posterior 估計中接受的度量數目。


### <a name="maxmeasurements--int"></a>maxMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

在作業被視為失敗之前所能執行的測量總數。


### <a name="unwind--int"></a>回溯： [Int](xref:microsoft.quantum.lang-ref.int)

一致性檢查失敗時所要記住的結果數目。


### <a name="oracle--continuousoracle"></a>oracle： [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

代表單一 $U $ 的作業，例如 $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $，但有未知的階段 $ \phi \in \mathbb{R} ^ + $。


### <a name="targetstate--qubit"></a>targetState： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

$U $ act 的暫存器。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

最終的估計 $ \hat{\phi} \mathrel{： =} \expect [\phi] $，在此預期會將所有接受的資料放在「事後 posterior 上。

## <a name="remarks"></a>備註

### <a name="iterative-phase-estimation-and-eigenstates"></a>反復階段估計和 Eigenstates

一般而言，輸入暫存器 `eigenstate` 不需要是 $U $ 的 eigenstate $ \ket{\phi} $，但可以是 eigenstates 的迭加。 假設輸入狀態是由 \begin{align} \ket{\psi} & = \sum \_ {j} \Alpha \_ j \ket{\phi \_ j} 提供，\end{align} 其中 $ \{ \Alpha \_ j \} $ 是複雜的係數，例如 $ \sum \_ j | \Alpha \_ j | ^ 2 = $1，其中 $U \ket{\phi \_ j} = \phi \_ j\ket {\ phi \_ j} $。

然後，執行反復的階段估計最後會融合到單一 eigenstate，如 [開發指南](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates)中所述。

### <a name="experiment-design"></a>實驗設計

測量時間 $t $ 和反轉角度 $ \theta $ 傳遞給的物件 `oracle` ，是根據物件 *猜測啟發式*\Begin{align} \theta \sim \Pr ( \phi) ，\quad t \approx \frac {1} {\variance{\phi}}。
\end{align} 這種啟發學習法的最佳方式，是在一般之前的假設下，減少反復階段估計的預期「事後 posterior 變異數。

### <a name="optimality"></a>最優

這種作業接近階段 $ \phi $ 的最佳估算器，如使用二次遺失 $L ( \phi、\hat{\phi} ) \mathrel{： =} ( \phi-\hat{\phi} ) ^ $2。

如需反復階段估計統計資料的詳細資訊，請參閱 [貝氏階段估計](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) 。

## <a name="references"></a>參考資料

- Ferrie *et al.exe.* 2011 [doi： 10/tfx-cli](https://doi.org/10.1007/s11128-012-0407-6)， [arXiv： 1110.3067](https://arxiv.org/abs/1110.3067)。
- Wiebe *et al.exe.* 2013 [doi： 10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501)， [arXiv： 1309.0876](https://arxiv.org/abs/1309.0876)
- Wiebe 和 Granade 2018 *(準備)*。