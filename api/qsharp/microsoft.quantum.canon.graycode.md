---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699019"
---
# <a name="graycode-function"></a>GrayCode 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


建立灰色的程式碼序列

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>輸入

### <a name="n--int"></a>n： [Int](xref:microsoft.quantum.lang-ref.int)

位數



## <a name="output--intint"></a>輸出： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []

元組的陣列。 元組中的第一個值是元組中 GrayCode 序列第二個值的值，是目前值中要變更的位置，以取得下一個值。