---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: c32d7546fb753f78a72479cec11a6ed09c5e6179
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190729"
---
# <a name="applymajorityinplace-operation"></a>ApplyMajorityInPlace 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在量子位的註冊上就地套用三個量子位的多數作業。

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

這項作業會在3量子位上就地計算多數函數。

如果我們將輸出量子位表示為 $x $ 和 $y $ 的 $z $ 和輸入量子位，則作業會執行下列轉換： $ \ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x，y，z) } $。

## <a name="input"></a>輸入

### <a name="output--qubit"></a>輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)

第一個輸入量子位。 請注意，輸出會就地計算並儲存在此量子位中。


### <a name="input--qubit"></a>輸入： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

第二個和第三個輸入量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

