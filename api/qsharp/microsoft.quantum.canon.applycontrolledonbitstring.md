---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: ApplyControlledOnBitString 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 82adc74e23e1d50cb6436176a973fdd1a0eeb3bd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841937"
---
# <a name="applycontrolledonbitstring-operation"></a>ApplyControlledOnBitString 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在目標暫存器上套用單一作業，該作業是由指定之位遮罩所指定的狀態所控制。

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="bits--bool"></a>位： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

用來控制指定之單一作業的位字串。


### <a name="oracle--t--unit--is-adj--ctl"></a>oracle： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

要在目標注冊上套用的單一作業。


### <a name="controlregister--qubit"></a>controlRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

控制應用程式的量子暫存器 `oracle` 。


### <a name="targetregister--t"></a>targetRegister： t

要傳遞至做為輸入的目標暫存器 `oracle` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="remarks"></a>備註

指定的模式 `bits` 可能會縮短 `controlRegister` ，在這種情況下，會忽略額外的控制項量子位， (也就是，不會在 $ \ket {0} $ 和 $ \ket {1} $) 上控制。
如果超過 `bits` `controlRegister` ，則會引發錯誤。

例如， `bits = [0,1,0,0,1]` 表示 `oracle` 只有當 `controlRegister` 位於 state $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $ 時，才適用。