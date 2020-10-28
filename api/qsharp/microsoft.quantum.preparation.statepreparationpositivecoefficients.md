---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700402"
---
# <a name="statepreparationpositivecoefficients-function"></a>StatePreparationPositiveCoefficients 函式

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

包： [](https://nuget.org/packages/)


傳回可準備指定量子狀態的作業。

傳回的作業 $U $ 會從 $n $-量子位計算基礎狀態 $ \ket{0...0} $ 準備任意的量子狀態 $ \ket{\psi} $，其正係數 $ \ Alpha_j \ge $0。

在新配置的暫存器上執行的動作是由 $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ Alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ Alpha_j | ^ 2}}。
\end{align} $ $

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="coefficients--double"></a>係數： [Double](xref:microsoft.quantum.lang-ref.double)[]

最多 $ 2 ^ n $ 係數 $ \ Alpha_j $ 的陣列。 $J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。



## <a name="output--littleendian--unit-adj--ctl"></a>輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

狀態準備單一作業 $U $。

## <a name="remarks"></a>備註

負輸入係數 $ \ Alpha_j < $0 將視為具有值 $ | \ Alpha_j | $ 的正值。 `coefficients` 如果指定了少於 $ 2 ^ n $ 的元素，則會以 $ \ Alpha_j = $0.0 填補。