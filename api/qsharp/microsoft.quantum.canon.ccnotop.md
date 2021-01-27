---
uid: Microsoft.Quantum.Canon.CCNOTop
title: CCNOTop 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CCNOTop
qsharp.summary: The signature type of CCNOT gate.
ms.openlocfilehash: 40e1d719c89ba1e29d0b5cc0d443d94685835368
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852695"
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

