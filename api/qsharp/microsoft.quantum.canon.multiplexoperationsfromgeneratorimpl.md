---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGeneratorImpl
title: MultiplexOperationsFromGeneratorImpl 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGeneratorImpl
qsharp.summary: Implementation step of `MultiplexOperationsFromGenerator`.
ms.openlocfilehash: 68c9fcf7ee7893dc3ef6600cc5d6c5be807f9eb4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852474"
---
# <a name="multiplexoperationsfromgeneratorimpl-operation"></a>MultiplexOperationsFromGeneratorImpl 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


的執行步驟 `MultiplexOperationsFromGenerator` 。

```qsharp
operation MultiplexOperationsFromGeneratorImpl<'T> (unitaryGenerator : (Int, Int, (Int -> ('T => Unit is Adj + Ctl))), auxiliary : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="unitarygenerator--intintint---t--unit--is-adj--ctl"></a>unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int) -> t => [單位](xref:microsoft.quantum.lang-ref.unit)  是形容詞 + Ctl) 




### <a name="auxiliary--qubit"></a>輔助： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="index--littleendian"></a>index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)




### <a name="target--t"></a>目標： t





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="see-also"></a>另請參閱

- [Canon. MultiplexOperationsFromGenerator](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)