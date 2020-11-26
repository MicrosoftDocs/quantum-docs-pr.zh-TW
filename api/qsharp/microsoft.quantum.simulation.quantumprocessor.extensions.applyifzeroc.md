---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: ApplyIfZeroC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: 9a73ea9ec607bec89c996c096b235a72185b453d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230832"
---
# <a name="applyifzeroc-operation"></a>ApplyIfZeroC 操作

命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit is Ctl
```


## <a name="input"></a>輸入

### <a name="measurementresult--__invalidresult__"></a>measurementResult：__無效 <Result>__




### <a name="onresultzeroop--t--unit--is-ctl"></a>onResultZeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl




### <a name="zeroarg--t"></a>zeroArg： t





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

