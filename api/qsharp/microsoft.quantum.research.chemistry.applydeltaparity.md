---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: 40157b6a166b09c6fee63d86e203f92069d008f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225749"
---
# <a name="applydeltaparity-operation"></a>ApplyDeltaParity 操作

命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。

封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學


計算上一個 PQRS 之間的同位檢查差異 .。。詞彙和下一個 PQRS .。。術語。 這項差異是在輔助量子位上計算。

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="prevfermionicterm--int"></a>prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]

先前 PQRS 的索引清單 .。。條款。


### <a name="nextfermionicterm--int"></a>nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]

下一個 PQRS 的索引清單 .。。條款。


### <a name="aux--qubit"></a>aux： [量子位](xref:microsoft.quantum.lang-ref.qubit)

儲存同位計算結果的輔助量子位。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子位依所有 PQRS 的動作 .。。條款。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

這會假設 P 的索引 < Q < R < S < .。。適用于 prevPQ 和 nextPQ。