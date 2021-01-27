---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: ApplyMultiControlledC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: bf6b78cd18a827a9a4fd9d61dfd4d240de3503e9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844858"
---
# <a name="applymulticontrolledc-operation"></a>ApplyMultiControlledC 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


套用單一受控制作業的乘法受控制版本。
修飾詞 `C` 表示單一量子位作業是可控制的。

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>輸入

### <a name="singlycontrolledop--qubit--unit"></a>singlyControlledOp： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 

在單一量子位上控制的操作。
作業引數中的第一個量子位會假設為一個控制項，而其餘的會假設為目標量子位。
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

## <a name="references"></a>參考資料

- [*Michael Nielsen、Isaac Chuang*、量子計算和量子資訊](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>另請參閱

- [Canon. ApplyMultiControlledCA](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)