---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateC
title: PrepareChoiStateC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateC
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with a controlled variant onto given reference and target registers.
ms.openlocfilehash: b23b22fa4bf21ca48076ccda0db62b313f887aa9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700974"
---
# <a name="preparechoistatec-operation"></a>PrepareChoiStateC 操作

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

包： [](https://nuget.org/packages/)


使用受控制的變異數，針對指定的參考和目標暫存器，準備 Choi 對於– Jamiłkowski 狀態。

```qsharp
operation PrepareChoiStateC (op : (Qubit[] => Unit is Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="op--qubit--unit-ctl"></a>op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl




### <a name="reference--qubit"></a>參考： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [PrepareChoiState。](xref:Microsoft.Quantum.Preparation.PrepareChoiState)