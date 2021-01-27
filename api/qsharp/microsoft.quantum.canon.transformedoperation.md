---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9f564fee38fb22283da4807f829ddc5ec156bf3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852063"
---
# <a name="transformedoperation-function"></a>TransformedOperation 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定函式和作業之後，會傳回新的作業，其輸入會由指定的函式進行轉換。

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a>輸入

### <a name="fn--u---t"></a>fn： ' U-> t

將指定輸入轉換成作業預期格式的函式。


### <a name="op--t--unit"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 

要轉換的作業。



## <a name="output--u--unit"></a>輸出： ' U => [單位](xref:microsoft.quantum.lang-ref.unit) 

新的作業會 tbat 呼叫與其 `fn` 輸入，然後將產生的輸出傳遞給 `op` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要


### <a name="u"></a>' U



## <a name="example"></a>範例

下列呼叫會使用 @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" 將針對輸入設計的作業轉換為 @"Microsoft.Quantum.Arithmetic.BigEndian" 接受類型輸入的作業 @"Microsoft.Quantum.Arithmetic.LittleEndian" ：

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a>另請參閱

- [Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Canon. TransformedOperationC](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Canon 組成](xref:Microsoft.Quantum.Canon.Composed)