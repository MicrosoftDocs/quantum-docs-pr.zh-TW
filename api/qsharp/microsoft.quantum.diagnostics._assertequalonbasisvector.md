---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698203"
---
# <a name="_assertequalonbasisvector-operation"></a>_assertEqualOnBasisVector 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


檢查套用兩項作業的結果 `givenU` 和 `expectedU` 基礎狀態是否相同。 基礎狀態是由參數所描述 `basis` 。
<xref:microsoft.quantum.extensions.fliptobasis>如需此描述的詳細資訊，請參閱函式。

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>輸入

### <a name="basis--int"></a>基礎： [Int](xref:microsoft.quantum.lang-ref.int)[]

針對每個 $n $ 量子位，以單一量子位基礎狀態識別碼指定的基礎狀態 (0 <= 識別碼 <= 3) 。


### <a name="givenu--qubit--unit"></a>givenU： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 

要檢查 $n $ 量子位上的作業。


### <a name="expectedu--qubit--unit-adj"></a>expectedU： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

要與 givenU 比較的 $n $ 量子位上的參考作業。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

