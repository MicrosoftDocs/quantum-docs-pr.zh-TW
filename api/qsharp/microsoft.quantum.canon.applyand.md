---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: ApplyAnd 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699353"
---
# <a name="applyand-operation"></a>ApplyAnd 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


只有在這兩個控制項量子位都處於1狀態時，才使用度量來執行 adjoint 作業，以反轉指定的目標量子位。

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>描述

`target`只有當兩個控制項都是1，但假設處於狀態0時，才會反轉 `target` 。  作業具有 T 計數4、T 深度2且不需要協助程式量子位，因此如果已知為0，則可能較適合 CCNOT 作業 `target` 。  這項作業的 adjoint 是以測量為基礎，且不需要任何 T 閘道。

這項作業的受控制應用程式不需要協助程式量子位、閘道，也 `2^c` `Rz` 不會針對深度優化，其中 `c` 是整體控制量子位的數目，包括作業的兩個控制項 `ApplyAnd` 。  受 adjoint 控制的應用程式需要 `2^c - 1` `Rz` 兩個角度的閘道 () 非 adjoint 作業的大小、沒有協助程式量子位，且未針對深度優化。

## <a name="input"></a>輸入

### <a name="control1--qubit"></a>control1： [量子位](xref:microsoft.quantum.lang-ref.qubit)

第一個控制項量子位


### <a name="control2--qubit"></a>control2： [量子位](xref:microsoft.quantum.lang-ref.qubit)

第二個控制項量子位


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

目標輔助量子位;必須處於狀態0



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考

- Cody 的新穎結構： "容錯 Toffoli 閘道的結構"、Phys. A 87、022328、2013 [arXiv： 1212.5069](https://arxiv.org/abs/1212.5069) doi： 10.1103/PhysRevA. 87.022328
- Craig Gidney： "減半量子加法的成本"，量子2，頁面74，2018 [arXiv： 1709.06648](https://arxiv.org/abs/1709.06648) doi： 10.1103/PhysRevA. 85.044302
- Mathias Soeken：「量子 Oracle 電路和耶誕節樹狀結構模式」， [從2019年12月19日](https://msoeken.github.io/blog_qac.html) (注意：說明多個受控制的結構) 