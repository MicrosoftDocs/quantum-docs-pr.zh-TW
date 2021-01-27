---
uid: Microsoft.Quantum.Canon.Angle
title: Angle 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 0528f21b2d9c98b6497e28741964e6497d4d0fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842044"
---
# <a name="angle-function"></a>Angle 函數

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

