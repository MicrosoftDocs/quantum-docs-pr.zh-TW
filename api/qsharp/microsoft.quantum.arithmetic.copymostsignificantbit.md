---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699898"
---
# <a name="copymostsignificantbit-operation"></a>CopyMostSignificantBit 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


將代表不帶正負號整數的量子位暫存器最重要的位複製 `from` 到量子位中 `target` 。

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="from--littleendian"></a>來源： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

從中複製最大位的不帶正負號整數。
以位元組由小到大格式編碼的整數。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

要在其中複製最大位的量子位。 位編碼是以計算為基礎。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [LittleEndian。](xref:Microsoft.Quantum.Arithmetic.LittleEndian)