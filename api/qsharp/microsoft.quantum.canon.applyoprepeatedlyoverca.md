---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverCA
title: ApplyOpRepeatedlyOverCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverCA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: b7d401f323d7affc27697744bb659c687e252682
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209103"
---
# <a name="applyoprepeatedlyoverca-operation"></a>ApplyOpRepeatedlyOverCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將相同的 op 套用至量子位登錄多次。

```qsharp
operation ApplyOpRepeatedlyOverCA (op : (Qubit[] => Unit is Adj + Ctl), targets : Int[][], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="op--qubit--unit--is-adj--ctl"></a>op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

要在量子位暫存器上多次套用的作業


### <a name="targets--int"></a>目標： [Int](xref:microsoft.quantum.lang-ref.int)[] []

描述 op 目標的嵌套陣列。 每個陣列都應該包含描述要使用之量子位的整數清單。


### <a name="register--qubit"></a>register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要處理的量子位 register。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [Canon. ApplySeriesOfOps](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)