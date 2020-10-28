---
uid: Microsoft.Quantum.Canon.CCNOTop
title: CCNOTop 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CCNOTop
qsharp.summary: The signature type of CCNOT gate.
ms.openlocfilehash: 026a368b753a1b3e74b8e4352cf65835546df4bc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699081"
---
# <a name="ccnotop-user-defined-type"></a>CCNOTop 使用者定義型別

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


CCNOT 閘道的簽名類型。

```qsharp

newtype CCNOTop = (Apply : ((Qubit, Qubit, Qubit) => Unit is Adj));
```



## <a name="named-items"></a>命名專案

### <a name="apply--qubitqubitqubit--unit-adj"></a>Apply： ([量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

