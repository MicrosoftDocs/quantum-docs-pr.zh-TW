---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 5b8afe222d197eb7d342ac45f027f2de9130b61a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697967"
---
# <a name="fivequbitcoderecoveryfn-function"></a>FiveQubitCodeRecoveryFn 函式

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [](https://nuget.org/packages/)


傳回函式，此函式會將錯誤的症狀度量對應至⟦5，1，3⟧量副程式代碼的資料表查閱適當的錯誤更正 Pauli 運算子。

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>輸出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

型別為 `RecoveryFn` 的函式，它會接受發生症狀測量 `Result[]` ，並傳回 `Pauli[]` 可更正偵測到之錯誤的運算子。

## <a name="remarks"></a>備註

藉由逐一查看權數 $1 $ 的所有錯誤，我們總共取得了 $ 3 \ 乘以 5 = 15 $ 的非一般 syndromes。
與身分識別一起，會建立錯誤資料表和對應的症狀。 在5個量子位程式碼中，此資料表是由所提供： $X \_ 1： (0、0、0、1) ;X \_ 2： (1、0、0、0) ;X \_ 3： (1、1、0、0) ;X \_ 4： (0、1、1、0) ;X \_ 5： (0、0、1、1) $、$Z \_ 1： (1、0、1、0) ;Z \_ 2： (0、1、0、1) ;Z \_ 3： (0、0、1、0) ;Z \_ 4： (1、0、0、1) ;Z \_ 5： (0、1、0、0) $，$Y _i $，方法是新增 $X _i $ 和 $Z _i $ syndromes。 請注意，資料表查閱復原中的順序是藉由將 bitvectors 轉換為整數 (使用位元組由小到大的) 來提供。

## <a name="see-also"></a>另請參閱

- [ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)