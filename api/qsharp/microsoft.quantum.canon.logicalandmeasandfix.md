---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698985"
---
# <a name="logicalandmeasandfix-operation"></a>LogicalANDMeasAndFix 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


計算多個量子位的邏輯 AND。

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="ctrlregister--qubit"></a>ctrlRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子位輸入至多個輸入和閘道。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

量子位，以及寫入的輸出。 這會假設一律以 $ \ket {0} $ 狀態開始。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

當 `ctrlRegister` 只有 $2 $ 量子位時，這相當於作業， `CCNOT` 但階段 $e ^ {i \ Pi/2} $ on $ \ket {001} $ 和 $-e ^ {i \ pi/2} $ on $ \ket {101} $ 和 $ \ket {011} $。
Adjoint 也是測量和修復方法，它只是在特殊情況下的原始作業反向 (請參閱) 的參考，但使用較少的 T 閘道。

## <a name="references"></a>參考

- [*Craig Gidney* ，1709.06648](https://arxiv.org/abs/1709.06648)