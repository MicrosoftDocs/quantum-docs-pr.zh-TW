---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: _JWOptimizedZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: 8bbd4af0389a7b748be11dc50bacd2c178521adc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700898"
---
# <a name="_jwoptimizedz-operation"></a>_JWOptimizedZ 操作

命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。

包： [](https://nuget.org/packages/)


在階段估計中將 Rz 旋轉（具有 C-NOT 技巧）套用至雙階段。

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="angle--double"></a>角度： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

Rz 旋轉的角度。


### <a name="parityqubit--qubit"></a>parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)

量子位，決定時間演進的正負號。


### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

