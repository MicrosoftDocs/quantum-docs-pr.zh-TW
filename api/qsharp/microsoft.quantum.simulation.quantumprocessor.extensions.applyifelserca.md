---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRCA
title: ApplyIfElseRCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRCA
qsharp.summary: ''
ms.openlocfilehash: 6fbf186575775b3ae18a41727c225fb871f8dac0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192616"
---
# <a name="applyifelserca-operation"></a>ApplyIfElseRCA 操作

命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyIfElseRCA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj + Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj + Ctl), oneArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="measurementresult--__invalidresult__"></a>measurementResult：__無效 <Result>__




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a>onResultZeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl




### <a name="zeroarg--t"></a>zeroArg： t




### <a name="onresultoneop--u--unit--is-adj--ctl"></a>onResultOneOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl




### <a name="onearg--u"></a>oneArg： ' U





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要


### <a name="u"></a>' U

