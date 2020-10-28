---
uid: Microsoft.Quantum.Intrinsic.Reset
title: 重設作業
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: c89cbbce49e294e56abc11b3b0492d2ed8e980a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699783"
---
# <a name="reset-operation"></a>重設作業

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

包： [](https://nuget.org/packages/)


假設有一個量子位，請加以測量，並確保其處於 | 0 ⟩狀態，讓它可以安全地發行。

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

量子位，其狀態會重設為 $ \ket {0} $。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

