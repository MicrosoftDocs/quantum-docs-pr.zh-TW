---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: d44c462c7a9fc9521bdecfe2ca7f607e90482baf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845228"
---
# <a name="andladder-operation"></a>AndLadder 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在目標量子位的註冊上執行受控制的「和階梯」。

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a>描述

這項作業會套用依下列計算方式對應的轉換：計算基礎： $ $ \begin{align} \ket{x \_ 1、\dots ..、x \_ n} \ket{y \_ 1、\dots ..、y \_ {n-1}} \mapsto \ket{x \_ 1、\dots ..、x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2) \dots ..、y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}、\end{align} $ $，其中 $ \ket{x \_ 1、\dots ..、x \_ n} $ 指的是的計算基礎狀態 `controls` ，其中 $ \ket{y \_ 1、\dots ..、y \_ {n-1}} $ 指的是的計算基礎狀態 `targets` 。

## <a name="input"></a>輸入

### <a name="ccnot--ccnotop"></a>ccnot： [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

要用於結構的 CCNOT 閘道。


### <a name="controls--qubit"></a>控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要當做和階梯控制項使用的量子位暫存器。
這項作業會保留非變異的計算基礎狀態 `controls` 。
的長度 `controls` 必須至少為2，而且必須等於1加上的長度 `targets` 。


### <a name="targets--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

的長度 `targets` 必須至少為1，且長度必須等於 `controls` 減號一。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

- 當做和的一部分使用 <xref:microsoft.quantum.canon.applymulticontrolledc> <xref:microsoft.quantum.canon.applymulticontrolledca> 。
- 如需說明和電路圖表，請參閱 Nielsen & Chuang 中的圖4.10，第4.3 節。

## <a name="references"></a>參考資料

- [*Michael Nielsen、Isaac Chuang*、量子計算和量子資訊](http://doi.org/10.1017/CBO9780511976667)