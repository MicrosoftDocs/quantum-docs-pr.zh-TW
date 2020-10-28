---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697971"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode 函式

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [](https://nuget.org/packages/)


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