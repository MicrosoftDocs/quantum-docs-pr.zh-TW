---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699335"
---
# <a name="applycontrolledonint-operation"></a>ApplyControlledOnInt 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


如果控制項暫存器狀態對應到指定的正整數，則在目標暫存器上套用單一作業。

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>輸入

### <a name="numberstate--int"></a>numberState： [Int](xref:microsoft.quantum.lang-ref.int)

應控制作業的非負整數 `oracle` 。


### <a name="oracle--t--unit-adj--ctl"></a>oracle： t => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

要控制的單一作業。


### <a name="controlregister--qubit"></a>controlRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

控制應用程式的量子暫存器 `oracle` 。


### <a name="targetregister--t"></a>targetRegister： t

要套用的註冊 `oracle` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="remarks"></a>備註

的值 `numberState` 是使用位元組由大到小的編碼來解讀。

`numberState` 最多隻能有 $ 2 ^ \texttt{Length (controlRegister) }-$1。
例如， `numberState = 537` 表示 `oracle` 只有當 `controlRegister` 處於狀態 $ \ket $ 時，才適用 {537} 。