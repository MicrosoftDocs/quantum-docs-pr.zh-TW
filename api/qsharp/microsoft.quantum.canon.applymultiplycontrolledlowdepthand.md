---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 1aeab429bd6304c621e0d5225b43a76eab607c84
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209191"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a>ApplyMultiplyControlledLowDepthAnd 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


假設目標量子位已初始化為0，則會執行多個控制的 Toffoli 閘道。  Adjoint 作業會假設目標量子位將重設為0。  需要 Rz 深度為1，而協助程式量子位的數目是量子位數目的指數。

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a>輸入

### <a name="controls--qubit"></a>控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

控制項量子位


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

目標量子位



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

