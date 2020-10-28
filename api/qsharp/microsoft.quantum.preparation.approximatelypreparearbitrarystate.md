---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: ApproximatelyPrepareArbitraryState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 2561b098c5faf2d24bb9ab348fb052025808e441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700742"
---
# <a name="approximatelypreparearbitrarystate-operation"></a>ApproximatelyPrepareArbitraryState 操作

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

包： [](https://nuget.org/packages/)


假設有一組係數和位元組由小到大編碼的量子暫存器，請在該暫存器上備妥指定係數所描述的狀態，直到指定的近似值容錯。

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>描述

這種作業會準備具有複雜係數 $r _j e ^ {i t_j} $ 的任意量子狀態 $ \ket{\psi} $，$n $-量子位計算基礎狀態 $ \ket{0 \cdots 0} $。
尤其是，這項作業的動作可以透過單一轉換 $U $ 來模擬，而這會在全-零的狀態下運作，如下所示：

$ $ \begin{align} U\ket {0 ... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。
\end{align} $ $

## <a name="input"></a>輸入

### <a name="tolerance--double"></a>容錯： [Double](xref:microsoft.quantum.lang-ref.double)

準備指定的狀態時，所要使用的近似值容錯。


### <a name="coefficients--complexpolar"></a>係數： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

最多 $ 2 ^ n $ 複雜係數的陣列，以絕對值和階段 $ (r_j，t_j) $ 表示。 $J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。


### <a name="qubits--littleendian"></a>量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

以位元組由大到小的格式量子位註冊編碼編號狀態。 這應該會在計算基礎狀態 $ \ket{0...0} $ 中初始化。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

負輸入係數 $r _j < $0 將被視為具有值 $ | r_j | $ 的正值。 `coefficients` 將會以 $ (r_j、t_j) = (0.0、0.0) $ 的元素填補，以指定小於 $ 2 ^ n $。

## <a name="references"></a>參考

- 量子邏輯電路的合成 Vivek V. Shende、Stephen S. Bullock、Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>另請參閱

- [ApproximatelyPrepareArbitraryState。](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)