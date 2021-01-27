---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845108"
---
# <a name="applycontrolledonint-operation"></a>ApplyControlledOnInt 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


如果控制項暫存器狀態對應到指定的正整數，則在目標暫存器上套用單一作業。

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="numberstate--int"></a>numberState： [Int](xref:microsoft.quantum.lang-ref.int)

應控制作業的非負整數 `oracle` 。


### <a name="oracle--t--unit--is-adj--ctl"></a>oracle： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

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