---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: c1801d1d7ed04ead11b672f24d44a94989cf8f1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699831"
---
# <a name="maj-operation"></a>MAJ 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


這會將就地操作的大部分作業套用至3量子位。

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>描述

如果我們將目標量子位的狀態表示為 $ \ket{z} $，而輸入量子位的輸入狀態為 $ \ket{x} $ 和 $ \ket{y} $，則這項作業會執行下列轉換： $ \ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x，y，z) } $。

## <a name="input"></a>輸入

### <a name="input0--qubit"></a>input0： [量子位](xref:microsoft.quantum.lang-ref.qubit)

第一個輸入量子位。


### <a name="input1--qubit"></a>input1： [量子位](xref:microsoft.quantum.lang-ref.qubit)

第二個輸入量子位。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

將套用多數函數的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

