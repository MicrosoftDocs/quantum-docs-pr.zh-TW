---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699065"
---
# <a name="composedoutput-function"></a>ComposedOutput 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


`inner`傳回指定輸入之和的組合輸出 `outer` 。

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>輸入

### <a name="outer--u---v"></a>外部： ' U-> ' V




### <a name="inner--t---u"></a>內部： t-> ' U




### <a name="target--t"></a>目標： t





## <a name="output--v"></a>輸出： ' V



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要


### <a name="u"></a>' U


### <a name="v"></a>' V

