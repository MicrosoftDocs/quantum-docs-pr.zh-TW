---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: a506ccb637b331a392ea75383c8bd605114af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202935"
---
# <a name="rmencoding-function"></a>RMEncoding 函式

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


{-1,1} 布林值真值的編碼

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a>輸入

### <a name="b--bool"></a>b： [Bool](xref:microsoft.quantum.lang-ref.bool)

布林值



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

如果 `b` 為 false，則為1，否則為-1