---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: ApplyWithInputTransformationA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b72c131691e08b4bd32b7faf9265aad6c52b7fde
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699117"
---
# <a name="applywithinputtransformationa-operation"></a>ApplyWithInputTransformationA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


假設有接受一些輸入的作業，傳回與該作業相容之輸出的函式，以及該函式的輸入，則會使用函式來套用作業，以將輸入轉換成作業預期的表單。

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit
```


## <a name="input"></a>輸入

### <a name="fn--u---t"></a>fn： ' U-> t

將指定輸入轉換成作業預期格式的函式。


### <a name="op--t--unit-adj"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

要套用的作業。


### <a name="input--u"></a>輸入： ' U

函數的輸入。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要


### <a name="u"></a>' U



## <a name="see-also"></a>另請參閱

- [Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Canon. ApplyWithInputTransformationC](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Canon. ApplyWithInputTransformationCA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)