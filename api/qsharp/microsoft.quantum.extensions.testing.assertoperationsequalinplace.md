---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualInPlace has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 64cc1e5c78af100b652ced24f00f3097c35ea5d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98820229"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace 操作

命名空間： [Microsoft. 副檔名. 測試](xref:Microsoft.Quantum.Extensions.Testing)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


> [!WARNING]
> AssertOperationsEqualInPlace 已被取代。 請改用 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace>。
>
> 請使用 @"microsoft.quantum.diagnostics.assertoperationsequalinplace"。
> 請注意，此作業的引數順序已變更。



```qsharp
operation AssertOperationsEqualInPlace (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--qubit--unit"></a>實際： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 




### <a name="expected--qubit--unit--is-adj"></a>預期： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞




### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

