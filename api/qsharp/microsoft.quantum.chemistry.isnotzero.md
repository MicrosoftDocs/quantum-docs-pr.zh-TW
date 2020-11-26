---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204057"
---
# <a name="isnotzero-function"></a>IsNotZero 函式

命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


檢查某個 `Double` 數位是否大約為零。

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>輸入

### <a name="number--double"></a>數位： [Double](xref:microsoft.quantum.lang-ref.double)

要檢查的數位



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

如果的 `number` 絕對值大於，則傳回 true `1e-15` 。