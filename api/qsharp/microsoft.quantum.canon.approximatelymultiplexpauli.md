---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: ApproximatelyMultiplexPauli 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 1fc8a8857b6b37d4c3e812a3c4cb2941b9238800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844578"
---
# <a name="approximatelymultiplexpauli-operation"></a>ApproximatelyMultiplexPauli 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在量子位陣列上套用 Pauli 旋轉，並根據指定的承受度截斷小旋轉角度。

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

這會套用一個受控制的單一作業，此作業會在由 $n $-量子位 number state $ \ket{j} $ 控制時，對單一量子位 Pauli 運算子 $P $ 執行旋轉（依角度 $ \ theta_j $）。
尤其是這項作業的動作是由單一

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}。
\end{align}

##

## <a name="input"></a>輸入

### <a name="tolerance--double"></a>容錯： [Double](xref:microsoft.quantum.lang-ref.double)

低於的容錯會被截斷。


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

- [Canon. MultiplexPauli](xref:Microsoft.Quantum.Canon.MultiplexPauli)