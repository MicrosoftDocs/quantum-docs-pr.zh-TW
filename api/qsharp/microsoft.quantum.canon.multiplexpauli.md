---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: MultiplexPauli 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: 0714e796c1e5ad097814bcf507f49f59a844e9ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698955"
---
# <a name="multiplexpauli-operation"></a>MultiplexPauli 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


在量子位的陣列上套用 Pauli 旋轉。

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a>描述

這會套用一個受控制的單一作業，此作業會在由 $n $-量子位 number state $ \ket{j} $ 控制時，對單一量子位 Pauli 運算子 $P $ 執行旋轉（依角度 $ \ theta_j $）。
尤其是這項作業的動作是由單一

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}。
\end{align} $ $

## <a name="input"></a>輸入

### <a name="coefficients--double"></a>係數： [Double](xref:microsoft.quantum.lang-ref.double)[]

最多 $ 2 ^ n $ 係數 $ \ theta_j $ 的陣列。 $J $ th 係數會以位元組由大到小的格式來編制數位狀態 $ \ket{j} $ 編碼。


### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli 運算子 $P $，可決定旋轉軸。


### <a name="control--littleendian"></a>控制項： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

以位元組由大到小的格式，$n $ 量子位 control register 編碼數位狀態 $ \ket{j} $。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

由 $e ^ {i P \ theta_j} $ 旋轉的單一量子位註冊。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

`coefficients` 如果指定了少於 $ 2 ^ n $ 的元素，則會以 $ \ theta_j = $0.0 填補。

## <a name="see-also"></a>另請參閱

- [Canon. ApproximatelyMultiplexPauli](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)