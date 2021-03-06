---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841697"
---
# <a name="applylowdepthand-operation"></a>ApplyLowDepthAnd 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


只有在這兩個控制項量子位都是在1狀態下（具有 T-深度1），並使用度量來執行 adjoint 作業時，才會反轉指定的目標量子位。

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

`target`只有當兩個控制項都是1，但假設處於狀態0時，才會反轉 `target` 。  作業具有 T 計數4、T 深度1，且需要一個協助程式量子位，因此如果已知為0，則可能較適合 CCNOT 作業 `target` 。  這項作業的 adjoint 是以測量為基礎，且不需要任何 T 閘道，也不需要協助程式量子位。

## <a name="input"></a>輸入

### <a name="control1--qubit"></a>control1： [量子位](xref:microsoft.quantum.lang-ref.qubit)

第一個控制項量子位


### <a name="control2--qubit"></a>control2： [量子位](xref:microsoft.quantum.lang-ref.qubit)

第二個控制項量子位


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

目標輔助量子位;必須處於狀態0



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考資料

- Cody 的新穎結構： "容錯 Toffoli 閘道的結構"、Phys. A 87、022328、2013 [arXiv： 1212.5069](https://arxiv.org/abs/1212.5069) doi： 10.1103/PhysRevA. 87.022328
- Peter Selinger：「T 深度1的量子線路」，Phys. A 87、042302、2013 [arXiv： 1210.0974](https://arxiv.org/abs/1210.0974) doi： 10.1103/PhysRevA. 87.042302