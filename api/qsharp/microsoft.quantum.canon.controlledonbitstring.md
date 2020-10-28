---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: ca5a6e116eff187060f7a160e42836b170f0362d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699059"
---
# <a name="controlledonbitstring-function"></a>ControlledOnBitString 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


傳回在目標暫存器上套用 oracle 的單一作業（如果控制項暫存器狀態對應到指定的位元遮罩）。

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>描述

此函式的輸出是可由單一轉換 $U $ 表示的運算，例如 \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1} ) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{cases} \end{align}，其中 $V $ 是代表操作動作的單一轉換 `oracle` 。

## <a name="input"></a>輸入

### <a name="bits--bool"></a>位： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

用來控制指定之單一作業的位字串。


### <a name="oracle--t--unit-adj--ctl"></a>oracle： t => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

要在目標注冊上套用的單一作業。



## <a name="output--qubitt--unit-adj--ctl"></a>Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，t) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

`oracle`當控制項暫存器狀態對應至位元遮罩時，會在目標暫存器上套用的單一作業 `bits` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="remarks"></a>備註

指定的模式 `bits` 可能會縮短 `controlRegister` ，在這種情況下，會忽略額外的控制項量子位， (也就是，不會在 $ \ket {0} $ 和 $ \ket {1} $) 上控制。
如果超過 `bits` `controlRegister` ，則會引發錯誤。

指定布林值陣列 `bits` 和單一作業 `oracle` 之後，此函式的輸出就是執行下列步驟的作業：

* 將作業套用 `X` 至控制項暫存器（對應至的元素）的每個量子位 `false` `bits` ;
* 適用于 `Controlled oracle` 控制項和目標暫存器;
* 將作業套用 `X` 至控制項暫存器的每個量子位，以再次對應至的專案，以將控制項暫存器傳回 `false` `bits` 至原始狀態。

仿函數的輸出 `Controlled` 是的特殊案例， `ControlledOnBitString` 其中 `bits` 等於 `[true, ..., true]` 。