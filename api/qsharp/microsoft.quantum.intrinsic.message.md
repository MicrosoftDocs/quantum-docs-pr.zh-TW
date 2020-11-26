---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199007"
---
# <a name="message-function"></a>Message 函數

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


記錄訊息。

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a>輸入

### <a name="msg--string"></a>msg： [String](xref:microsoft.quantum.lang-ref.string)

要報告的訊息。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

此函式的特定行為與模擬器相依，但在大部分情況下，會將指定的訊息寫入主控台。