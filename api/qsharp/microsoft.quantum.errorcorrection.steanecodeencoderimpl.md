---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697927"
---
# <a name="steanecodeencoderimpl-operation"></a>SteaneCodeEncoderImpl 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [](https://nuget.org/packages/)


私用作業可用來同時執行 Steane 程式碼編碼器和解碼器。

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="data--qubit"></a>data： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

保留1個量子位的陣列，也就是輸入量子位。


### <a name="scratch--qubit"></a>臨時： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

保留6個量子位的陣列，這會增加冗余。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

