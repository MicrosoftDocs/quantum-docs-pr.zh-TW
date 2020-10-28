---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699022"
---
# <a name="fst-function"></a>Fst 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


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