---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699322"
---
# <a name="applyfermionicswap-operation"></a>ApplyFermionicSWAP 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


套用 Fermionic 交換。

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a>描述

這基本上會交換量子位，同時套用-1 的全域階段（如果兩個量子位都是1）。 保留 orbitals 的反 symmetrization。
如需詳細資訊，請參閱。

這項作業是以單一運算子 \begin{align} f_ {swap} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}。
\end{align}

## <a name="input"></a>輸入

### <a name="qubit1--qubit"></a>qubit1： [量子位](xref:microsoft.quantum.lang-ref.qubit)

要交換的第一個量子位。


### <a name="qubit2--qubit"></a>qubit2： [量子位](xref:microsoft.quantum.lang-ref.qubit)

要交換的第二個量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考

- [*Ryan Babbush、Nathan Wiebe、Jarrod McClean、James McClain、Hartmut Neven、Garnet Kin-Lic Chan* 、arXiv：1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>另請參閱

- [。 SWAP](xref:Microsoft.Quantum.Intrinsic.SWAP)