---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 1d0efa7b83d2e8e75c4b293866f3929f357ec44b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210364"
---
# <a name="statepreparationcomplexcoefficients-function"></a>StatePreparationComplexCoefficients 函式

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> StatePreparationComplexCoefficients 已被取代。 請改用 <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP>。

傳回準備特定量子狀態的作業。

傳回的作業 $U $ 會準備具有複雜係數的任意量子狀態 $ \ket{\psi} $ $r _j e ^ {i t_j} $，從 $n $-量子位計算基礎狀態 $ \ket{0...0} $。

以 $ $ \begin{align} U\ket {0 ... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}} 為新配置的暫存器提供的動作。
\end{align} $ $

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="coefficients--complexpolar"></a>係數： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

最多 $ 2 ^ n $ 複雜係數的陣列，以絕對值和階段 $ (r_j，t_j) $ 表示。 $J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。



## <a name="output--littleendian--unit--is-adj--ctl"></a>輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

狀態準備單一作業 $U $。

## <a name="remarks"></a>備註

負輸入係數 $r _j < $0 將被視為具有值 $ | r_j | $ 的正值。 `coefficients` 將會以 $ (r_j、t_j) = (0.0、0.0) $ 的元素填補，以指定小於 $ 2 ^ n $。