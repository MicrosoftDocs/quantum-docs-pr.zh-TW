---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: TrotterArbitraryImplCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1c094d09ac8bdd71a59ef57d8715a6f90f18efc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698814"
---
# <a name="trotterarbitraryimplca-operation"></a>TrotterArbitraryImplCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


偶數 Trotter – Suzuki 整合器的遞迴執行。

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a>輸入

### <a name="order--int"></a>order： [Int](xref:microsoft.quantum.lang-ref.int)

Trotter-Suzuki 整合者的順序。


### <a name="nsteps--int"></a>nSteps： [Int](xref:microsoft.quantum.lang-ref.int)

要分解為時間步驟的作業數目。


### <a name="op--intdoublet--unit-adj--ctl"></a>op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl

接受索引輸入的作業 (類型 `Int`) 和時間輸入 (類型 `Double`) ，以及量子暫存器 (類型) ， `'T` 以進行分解。


### <a name="stepsize--double"></a>stepSize： [Double](xref:microsoft.quantum.lang-ref.double)

模擬的每個步驟大小的乘數。


### <a name="target--t"></a>目標： t

作業作用所在的量子暫存器。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

每次步驟應採取的型別;通常是 `Qubit[]` 或 `Qubit` 。