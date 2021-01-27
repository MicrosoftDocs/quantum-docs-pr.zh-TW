---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852818"
---
# <a name="applyblockencodingbylcu-operation"></a>ApplyBlockEncodingByLCU 操作

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


`BlockEncodingByLCU` 的實作。

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="statepreparation--t--unit--is-adj--ctl"></a>statePreparation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl




### <a name="selector--ts--unit--is-adj--ctl"></a>選取器： ( t，) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl




### <a name="auxiliary--t"></a>輔助： t




### <a name="system--s"></a>system：





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要


### <a name="s"></a>者

