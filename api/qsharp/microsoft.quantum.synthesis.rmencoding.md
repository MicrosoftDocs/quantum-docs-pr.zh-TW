---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: ef9be0f0628c8ba8c5f131cc558bdcda6bb6ea55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701139"
---
# <a name="rmencoding-function"></a>RMEncoding 函式

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

包： [](https://nuget.org/packages/)


{-1,1} 布林值真值的編碼

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a>輸入

### <a name="b--bool"></a>b： [Bool](xref:microsoft.quantum.lang-ref.bool)

布林值



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

如果 `b` 為 false，則為1，否則為-1