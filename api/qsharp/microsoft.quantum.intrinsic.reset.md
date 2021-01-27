---
uid: Microsoft.Quantum.Intrinsic.Reset
title: 重設作業
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: b4275796b966bfe7f55271f4e92866410a14e830
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818635"
---
# <a name="reset-operation"></a>重設作業

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


假設有一個量子位，請加以測量，並確保其處於 | 0 ⟩狀態，讓它可以安全地發行。

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

量子位，其狀態會重設為 $ \ket {0} $。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

