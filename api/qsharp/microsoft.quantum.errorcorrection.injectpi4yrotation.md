---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 4ff0abe67a6d18204e417a45f8d8f1d092d02b88
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200793"
---
# <a name="injectpi4yrotation-operation"></a>InjectPi4YRotation 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


旋轉 Y 軸上的單一量子位與π/4。

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a>描述

執行有關的π/4 旋轉 `Y` 。

旋轉是藉由使用魔術狀態來執行;也就是狀態 $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket 的複本 {8} {1} 。
\end{align} $ $

## <a name="input"></a>輸入

### <a name="data--qubit"></a>資料： [量子位](xref:microsoft.quantum.lang-ref.qubit)

要 $Y $ \pi/$4 旋轉的量子位。


### <a name="magic--qubit"></a>魔術： [量子位](xref:microsoft.quantum.lang-ref.qubit)

一開始是魔術狀態的量子位。 這項作業的下列應用程式 `magic` 會傳回 $ \ket {0} $ 狀態。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

以下是相等的：

```qsharp
Ry(PI() / 4.0, data);
```

及

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

這項作業支援 `Adjoint` 仿函數，在此情況下會使用相同的魔術狀態，但對資料量子位的影響是 $-\ pi/4 $ $Y $-旋轉。