---
uid: Microsoft.Quantum.Characterization.ApplyHadamardTestOnSingleRegister
title: ApplyHadamardTestOnSingleRegister 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ApplyHadamardTestOnSingleRegister
qsharp.summary: ''
ms.openlocfilehash: d61912d3681f7a6462f4b25aaf800483aecbee01
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204448"
---
# <a name="applyhadamardtestonsingleregister-operation"></a>ApplyHadamardTestOnSingleRegister 操作

命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyHadamardTestOnSingleRegister (phaseShift : Bool, commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>輸入

### <a name="phaseshift--bool"></a>phaseShift： [Bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="commonpreparation--qubit--unit--is-adj"></a>commonPreparation： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞




### <a name="preparation1--qubit--unit--is-adj--ctl"></a>preparation1： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl




### <a name="preparation2--qubit--unit--is-adj--ctl"></a>preparation2： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl




### <a name="register--qubit"></a>register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

