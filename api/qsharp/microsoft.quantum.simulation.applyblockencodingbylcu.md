---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700182"
---
# <a name="applyblockencodingbylcu-operation"></a>ApplyBlockEncodingByLCU 操作

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


`BlockEncodingByLCU` 的實作。

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a>輸入

### <a name="statepreparation--t--unit-adj--ctl"></a>statePreparation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl




### <a name="selector--ts--unit-adj--ctl"></a>選取器： ( t，) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl




### <a name="auxiliary--t"></a>輔助： t




### <a name="system--s"></a>system：





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要


### <a name="s"></a>者

