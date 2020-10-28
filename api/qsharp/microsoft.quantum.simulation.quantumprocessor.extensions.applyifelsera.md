---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRA
title: ApplyIfElseRA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRA
qsharp.summary: ''
ms.openlocfilehash: bcc52c6e2b4dfc6354e12c57e19739ac021d2e8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701122"
---
# <a name="applyifelsera-operation"></a>ApplyIfElseRA 操作

命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

包： [](https://nuget.org/packages/)




```qsharp
operation ApplyIfElseRA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj), oneArg : 'U)) : Unit
```


## <a name="input"></a>輸入

### <a name="measurementresult--__invalidresult__"></a>measurementResult： __無效 <Result>__




### <a name="onresultzeroop--t--unit-adj"></a>onResultZeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞




### <a name="zeroarg--t"></a>zeroArg： t




### <a name="onresultoneop--u--unit-adj"></a>onResultOneOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞




### <a name="onearg--u"></a>oneArg： ' U





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要


### <a name="u"></a>' U

