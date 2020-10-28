---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 21c9cdfc3b5b266cb3b93e52ee2fa4c655caf795
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698822"
---
# <a name="transformedoperationca-function"></a>TransformedOperationCA 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


指定函式和作業之後，會傳回新的作業，其輸入會由指定的函式進行轉換。

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="fn--u---t"></a>fn： ' U-> t

將指定輸入轉換成作業預期格式的函式。


### <a name="op--t--unit-adj--ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl

要轉換的作業。



## <a name="output--u--unit-adj--ctl"></a>輸出： ' U => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

新的作業會 tbat 呼叫與其 `fn` 輸入，然後將產生的輸出傳遞給 `op` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要


### <a name="u"></a>' U



## <a name="see-also"></a>另請參閱

- [Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Canon 組成](xref:Microsoft.Quantum.Canon.Composed)