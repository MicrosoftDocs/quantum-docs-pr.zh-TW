---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699055"
---
# <a name="controlledonint-function"></a>ControlledOnInt 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


傳回單一運算子，這個運算子會在目標暫存器上套用 oracle （如果控制項暫存器狀態對應到指定的正整數）。

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="numberstate--int"></a>numberState： [Int](xref:microsoft.quantum.lang-ref.int)

正整數。


### <a name="oracle--t--unit-adj--ctl"></a>oracle： t => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

單一運算子。



## <a name="output--qubitt--unit-adj--ctl"></a>Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，t) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

`oracle`如果控制項暫存器狀態對應至數位狀態，則會在目標暫存器上套用的單一運算子 `numberState` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="remarks"></a>備註

的值 `numberState` 是使用位元組由大到小的編碼來解讀。