---
uid: Microsoft.Quantum.Canon.Snd
title: Operators.snd 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: 11786fa195de12a7f2e4f2edb00ac0bc1071dd5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852163"
---
# <a name="snd-function"></a>Operators.snd 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


如果指定了配對，會傳回它的第二個元素。

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a>輸入

### <a name="pair--tu"></a>配對： ( t，' U) 

具有兩個元素的元組。



## <a name="output--u"></a>輸出： ' U

的第二個元素 `pair` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

配對第一個成員的類型。
### <a name="u"></a>' U

配對第二個成員的類型。