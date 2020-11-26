---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: ApplyConditionallyIntrinsicCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 2dd7a9b6e281c62470defa64685dc58872694468
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230186"
---
# <a name="applyconditionallyintrinsicca-operation"></a>ApplyConditionallyIntrinsicCA 操作

命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="measurementresults--__invalidresult__"></a>measurementResults：__無效 <Result>__ 的 []




### <a name="resultsvalues--__invalidresult__"></a>resultsValues：__無效 <Result>__ 的 []




### <a name="onequalop--unit--unit--is-adj--ctl"></a>onEqualOp： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl




### <a name="onnonequalop--unit--unit--is-adj--ctl"></a>onNonEqualOp： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

