---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697710"
---
# <a name="message-function"></a>Message 函數

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

包： [](https://nuget.org/packages/)


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