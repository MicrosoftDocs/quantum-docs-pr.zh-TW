---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 041fecfa27ae5bd17fa8fdc89ce964f985f6124b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853589"
---
# <a name="_assertequalonbasisvector-operation"></a>_assertEqualOnBasisVector 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

要與 givenU 比較的 $n $ 量子位上的參考作業。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

