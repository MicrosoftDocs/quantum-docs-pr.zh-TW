---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: ApplyConditionallyC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: fc1cf50b7befd40cf20720032329438715a9b856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699641"
---
# <a name="applyconditionallyc-operation"></a>ApplyConditionallyC 操作

命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

包： [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>輸入

### <a name="measurementresults--__invalidresult__"></a>measurementResults： __無效 <Result>__ 的 []




### <a name="resultsvalues--__invalidresult__"></a>resultsValues： __無效 <Result>__ 的 []




### <a name="onequalop--t--unit-ctl"></a>onEqualOp： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl




### <a name="equalarg--t"></a>equalArg： t




### <a name="onnonequalop--u--unit-ctl"></a>onNonEqualOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl




### <a name="nonequalarg--u"></a>nonEqualArg： ' U





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要


### <a name="u"></a>' U
