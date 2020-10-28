---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698015"
---
# <a name="bitfliprecoveryfn-function"></a>BitFlipRecoveryFn 函式

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [](https://nuget.org/packages/)


針對⟦3，1，1⟧位翻轉程式碼的資料表查閱，針對指定的 Pauli 作業進行的復原作業函數。

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>輸出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

型別為 `RecoveryFn` 的函式，它會接受發生症狀測量 `Result[]` ，並傳回 `Pauli[]` 可更正偵測到之錯誤的作業。

## <a name="see-also"></a>另請參閱

- [ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)