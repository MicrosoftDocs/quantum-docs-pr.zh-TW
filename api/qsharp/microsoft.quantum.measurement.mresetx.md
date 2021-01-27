---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 44459e681daf1d28ce7d45f91ad59059babe5716
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853748"
---
# <a name="mresetx-operation"></a>MResetX 操作

命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


以 X 為基礎測量單一量子位，並將它重設為遵循測量的固定初始狀態。

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a>描述

以 $X $ 基礎執行單一量子位量測，並確保量子位會在測量之後傳回 $ \ket {0} $。

## <a name="input"></a>輸入

### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

要測量的單一量子位。



## <a name="output--__invalidresult__"></a>輸出：__無效 <Result>__

`target`以 Pauli $X $ 基礎測量的結果。