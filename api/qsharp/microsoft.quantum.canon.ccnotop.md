---
uid: Microsoft.Quantum.Canon.CCNOTop
title: CCNOTop 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CCNOTop
qsharp.summary: The signature type of CCNOT gate.
ms.openlocfilehash: 533ea87e137aabf6f75e6096dc710ca15c984f25
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207474"
---
# <a name="ccnotop-user-defined-type"></a>CCNOTop 使用者定義型別

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


CCNOT 閘道的簽名類型。

```qsharp

newtype CCNOTop = (Apply : ((Qubit, Qubit, Qubit) => Unit is Adj));
```



## <a name="named-items"></a>命名專案

### <a name="apply--qubitqubitqubit--unit--is-adj"></a>Apply： ([量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

