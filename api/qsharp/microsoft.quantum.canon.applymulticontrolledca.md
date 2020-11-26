---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 28797583c23e21eb4bcae996a34c70ee06c6dbe8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209276"
---
# <a name="applymulticontrolledca-operation"></a>ApplyMultiControlledCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


套用單一受控制作業的乘法受控制版本。
修飾詞 `CA` 表示單一量子位作業是可控制且 adjointable 的。

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="singlycontrolledop--qubit--unit--is-adj"></a>singlyControlledOp： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

在單一量子位上控制的操作。
作業引數中的第一個量子位假設是一個控制項，而其餘的則假設為目標量子位。
`ApplyMultiControlled` 一律會呼叫長度至少為 `singlyControlledOp` 1 的引數。


### <a name="ccnot--ccnotop"></a>ccnot： [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

要用於此結構的受控制控制項-NOT 閘道。


### <a name="controls--qubit"></a>控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

`singlyControlledOp`要控制的量子位。
的長度 `controls` 必須至少為1。


### <a name="targets--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

作用的目標量子位 `singlyControlledOp` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

這種作業只會使用 clean ancilla 量子位。

如需說明和電路圖表，請參閱 Nielsen & Chuang 中的圖4.10，第4.3 節。

## <a name="references"></a>參考

- [*Michael Nielsen、Isaac Chuang*、量子計算和量子資訊](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>另請參閱

- [Canon. ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)