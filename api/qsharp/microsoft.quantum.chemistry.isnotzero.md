---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698682"
---
# <a name="isnotzero-function"></a>IsNotZero 函式

命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)

包： [](https://nuget.org/packages/)


檢查某個 `Double` 數位是否大約為零。

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>輸入

### <a name="number--double"></a>數位： [Double](xref:microsoft.quantum.lang-ref.double)

要檢查的數位



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

如果的 `number` 絕對值大於，則傳回 true `1e-15` 。