---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697907"
---
# <a name="syndromemeasop-user-defined-type"></a>SyndromeMeasOp 使用者定義型別

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [](https://nuget.org/packages/)


表示用來測量錯誤修正程式碼區塊之症狀的作業。

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a>備註

簽章 `(LogicalRegister => Syndrome)` 代表一項作業，該作業會共同在的量子位上運作 `LogicalRegister` ，而有些輔助量子位則接著輔助量子位的度量，以將 `Syndrome` 代表 `Result[]` 這些測量之的值解壓縮。

## <a name="see-also"></a>另請參閱

- [ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [ErrorCorrection 的症狀](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)