---
uid: Microsoft.Quantum.Canon.RAll0
title: RAll0 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 6185e66e08d2af3aa0b35791638820b4dcc5af35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698911"
---
# <a name="rall0-operation"></a>RAll0 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


執行階段移位操作。

$R = \boldone- (1-e ^ {i \phi} ) \ket{0\cdots 0} \bra{0\cdots 0} $。

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="phase--double"></a>階段： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

階段 $ \phi $ 已套用至 state $ \ket{0\cdots 0} \bra{0\cdots 0} $。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要 $R $ 旋轉其狀態的註冊。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [Canon. RAll1](xref:Microsoft.Quantum.Canon.RAll1)