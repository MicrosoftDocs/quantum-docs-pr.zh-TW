---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: StandardAmplitudeAmplification 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 984bfee89b6d79750228b8ca6aaf404f58aecd41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843936"
---
# <a name="standardamplitudeamplification-function"></a>StandardAmplitudeAmplification 函式

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


標準振幅放大演算法

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="niterations--int"></a>nIterations： [Int](xref:microsoft.quantum.lang-ref.int)

$n $ of 振幅放大的反覆運算次數


### <a name="stateoracle--stateoracle"></a>stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

準備開始狀態的單一 oracle $A $


### <a name="idxflagqubit--int"></a>idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)

索引至旗標量子位



## <a name="output--qubit--unit--is-adj--ctl"></a>輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

實作為標準振幅放大量子演算法的作業

## <a name="remarks"></a>備註

這是藉由 `AmpAmpPhasesStandard` 假設 \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} s + \sqrt{1-| \lambda | ^ 2} \ket f\cdots，所計算的一系列反映階段所取得的標準幅度放大演算法 \_ {0} \_ \end{align} 這項作業會在大部分情況下準備狀態 \begin{align} \Operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \Sin ( # B1 2n + 1) \sin ^ {-1} ( \lambda) # A5\ket {1} \_ f\ket {\ text {target}} \_ s + \cdots\ket {0} \_ f \end{align}， `flagQubit` 並且在 `auxiliaryRegister` 狀態 $ \ket {0} \_ f\ket {0} \_ a $ 中初始化。

## <a name="references"></a>參考資料

- [*G. Brassard、Hoyer、Mosca、Tapp*](https://arxiv.org/abs/quant-ph/0005055)