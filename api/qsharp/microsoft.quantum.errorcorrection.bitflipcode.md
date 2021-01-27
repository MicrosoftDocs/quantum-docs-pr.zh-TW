---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 0a5a028f85b80575b754b93a797a1460d21bb552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853200"
---
# <a name="bitflipcode-function"></a>BitFlipCode 函式

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回 QECC 值，表示⟦3、1、1⟧位翻轉程式碼編碼器，以及具有就地的症狀測量的解碼器。

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>輸出： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

藉由指定類型，傳回量子錯誤修正程式碼的執行 `QECC` 。