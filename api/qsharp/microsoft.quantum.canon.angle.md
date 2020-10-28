---
uid: Microsoft.Quantum.Canon.Angle
title: Angle 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699358"
---
# <a name="angle-function"></a>Angle 函數

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


如果的1為奇數，則傳回1，如果的值為1， `index` 則傳回-1 `index` 。

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>描述

值會對應至指定旋轉角度之指定指派的 n 變數和函式 Rademacher-Walsh 範圍之係數的正負號。

## <a name="input"></a>輸入

### <a name="index--int"></a>index： [Int](xref:microsoft.quantum.lang-ref.int)

輸入指派作為整數 (從0到 2 ^ n-1) 



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

