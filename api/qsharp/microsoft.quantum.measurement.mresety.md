---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 2e41e76a46b68178a8a22b39131d6ca2a8c50b64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854644"
---
# <a name="mresety-operation"></a>MResetY 操作

命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


以 Y 為單位測量單一量子位，並將它重設為遵循測量的固定初始狀態。

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a>描述

以 $Y $ 基礎執行單一量子位量測，並確保量子位會在測量之後傳回 $ \ket {0} $。

## <a name="input"></a>輸入

### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

要測量的單一量子位。



## <a name="output--__invalidresult__"></a>輸出：__無效 <Result>__

`target`以 Pauli $Y $ 基礎測量的結果。