---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840507"
---
# <a name="fst-function"></a>Fst 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


如果指定了配對，會傳回其第一個元素。

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a>輸入

### <a name="pair--tu"></a>配對： ( t，' U) 

具有兩個元素的元組。



## <a name="output--t"></a>輸出： t

`pair` 的第一個元素。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

配對第一個成員的類型。
### <a name="u"></a>' U

配對第二個成員的類型。