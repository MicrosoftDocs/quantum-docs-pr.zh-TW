---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697966"
---
# <a name="injectpi4yrotation-operation"></a>InjectPi4YRotation 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [](https://nuget.org/packages/)


旋轉 Y 軸上的單一量子位與π/4。

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
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