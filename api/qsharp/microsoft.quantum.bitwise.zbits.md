---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: f66b8ef0370e898dd1d095ff2840c91566f32cb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699365"
---
# <a name="zbits-function"></a>ZBits 函式

命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)

包： [](https://nuget.org/packages/)


傳回整數，表示 Pauli 運算子陣列的 Z 位。

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>輸入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Pauli 運算子的陣列，要以整數表示。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

整數 $x $ 具有二進位表示 $ (p_ {62} \, p_ {61} \, \dots .. \, p_0) $，其中 $p _i = $0，如果 `paulis[i]` 是 `PauliI` 或 `PauliX` ，則為 $p _i = $1 `paulis[i]` `PauliY` `PauliZ` 。

## <a name="remarks"></a>備註

如果陣列的長度大於63，函數將會擲回 `paulis` 。

## <a name="see-also"></a>另請參閱

- [XBits。](xref:Microsoft.Quantum.Bitwise.XBits)