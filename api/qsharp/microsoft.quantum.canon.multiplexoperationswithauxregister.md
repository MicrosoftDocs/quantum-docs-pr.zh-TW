---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: MultiplexOperationsWithAuxRegister 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: 91db22d6261709c1c3506c80ff600c904748575a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852468"
---
# <a name="multiplexoperationswithauxregister-operation"></a>MultiplexOperationsWithAuxRegister 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


MultiplexOperations 的執行步驟。

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="unitaries--t--unit--is-adj--ctl"></a>unitaries： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl []




### <a name="auxillaryregister--qubit"></a>auxillaryRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="index--littleendian"></a>index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)




### <a name="target--t"></a>目標： t





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="see-also"></a>另請參閱

- [Canon. MultiplexOperations](xref:Microsoft.Quantum.Canon.MultiplexOperations)