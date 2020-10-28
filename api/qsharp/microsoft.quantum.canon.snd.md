---
uid: Microsoft.Quantum.Canon.Snd
title: Operators.snd 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698859"
---
# <a name="snd-function"></a>Operators.snd 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


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