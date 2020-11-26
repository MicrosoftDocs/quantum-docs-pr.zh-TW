---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: RecoverCSS 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: eb01b1b9fccc19f0e3f1fd5ee596b95d0d61563f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200538"
---
# <a name="recovercss-operation"></a>RecoverCSS 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


依類型所描述的量副程式代碼，執行單次錯誤修正 `CSS` 。

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>輸入

### <a name="code--css"></a>程式碼： [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

封裝為類型的量子 CSS 錯誤修正程式碼 `CSS` 會描述量子資料的編碼和解碼，以及如何測量錯誤 syndromes。


### <a name="fnx--recoveryfn"></a>fnX： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`，會將每個 $X $ 錯誤的症狀對應到可 `Pauli[]` 更正偵測到之錯誤的作業。


### <a name="fnz--recoveryfn"></a>fnZ： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`，會將每個 $Z $ 錯誤的症狀對應到可 `Pauli[]` 更正偵測到之錯誤的作業。


### <a name="logicalregister--logicalregister"></a>logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

定義了穩定程式碼的量子位陣列。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [ErrorCorrection .CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)