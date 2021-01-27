---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: _JWOptimizedZ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: 76c96153b6baf8b593e0770a44b6190c075c8f53
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854240"
---
# <a name="_jwoptimizedz-operation"></a>_JWOptimizedZ 操作

命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。

封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學


在階段估計中將 Rz 旋轉（具有 C-NOT 技巧）套用至雙階段。

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="angle--double"></a>角度： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

Rz 旋轉的角度。


### <a name="parityqubit--qubit"></a>parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)

量子位，決定時間演進的正負號。


### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

