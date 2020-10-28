---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: ApplyConditionallyIntrinsicCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 7cdddba45824d5e5037270d8578f2cb16c03be83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699632"
---
# <a name="applyconditionallyintrinsicca-operation"></a>ApplyConditionallyIntrinsicCA 操作

命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

包： [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit
```


## <a name="input"></a>輸入

### <a name="measurementresults--__invalidresult__"></a>measurementResults： __無效 <Result>__ 的 []




### <a name="resultsvalues--__invalidresult__"></a>resultsValues： __無效 <Result>__ 的 []




### <a name="onequalop--unit--unit-ctl--adj"></a>onEqualOp： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞




### <a name="onnonequalop--unit--unit-ctl--adj"></a>onNonEqualOp： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

