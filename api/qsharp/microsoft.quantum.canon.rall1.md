---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 45892f9811faf56d7b9a0eb34e4bde0a32d5586d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698910"
---
# <a name="rall1-operation"></a>RAll1 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


執行階段移位操作。

$R = \boldone- (1-e ^ {i \phi} ) \ket{1\cdots 1} \bra{1\cdots 1} $。

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="phase--double"></a>階段： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

階段 $ \phi $ 已套用至 state $ \ket{1\cdots 1} \bra{1\cdots 1} $。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要 $R $ 旋轉其狀態的註冊。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

