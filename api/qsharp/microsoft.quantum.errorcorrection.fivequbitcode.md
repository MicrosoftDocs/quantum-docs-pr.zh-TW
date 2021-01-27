---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 540dcf1eafa7449f386676a9a3c9562a4d4bf29c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853148"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode 函式

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回 QECC 值，代表⟦5，1，3⟧代碼編碼器，以及具有就地發生症狀測量的解碼器。

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>輸出： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

藉由指定類型，傳回量子錯誤修正程式碼的執行 `QECC` 。

## <a name="remarks"></a>備註

下列兩份檔中找到此程式碼：

- C. H. Bennett、d. DiVincenzo、J. A。 Smolin 和 W. K。 Wootters、「混合狀態纏結與量子錯誤修正」、Phys. A、54 (1996) pp 3824-3851; https://arxiv.org/abs/quant-ph/9604024 和
- R. Laflamme、c. Miquel、J-phone。 巴斯和 W. H。 Zurek，「完美的量子錯誤矯正碼」 Phys Lett。 77 (1996) pp 198-201; https://arxiv.org/abs/quant-ph/9602019