---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: ApplyIfElseRC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 21069c43c16bc9712973ac4e0afea8320c0d83a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697150"
---
# <a name="applyifelserc-operation"></a>ApplyIfElseRC 操作

命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

包： [](https://nuget.org/packages/)




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a>輸入

### <a name="measurementresult--__invalidresult__"></a>measurementResult： __無效 <Result>__




### <a name="onresultzeroop--t--unit-ctl"></a>onResultZeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl




### <a name="zeroarg--t"></a>zeroArg： t




### <a name="onresultoneop--u--unit-ctl"></a>onResultOneOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl




### <a name="onearg--u"></a>oneArg： ' U





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要


### <a name="u"></a>' U

