---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: ddaace8df6e4c47c4affe2eeffb8d8ce31f37327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845238"
---
# <a name="xbits-function"></a>XBits 函式

命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傳回整數，表示 Pauli 運算子陣列的 X 位。

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>輸入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Pauli 運算子的陣列，要以整數表示。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

整數 $x $ 具有二進位表示 $ (p_ {62} \, p_ {61} \, \dots .. \, p_0) $，其中 $p _i = $0，如果 `paulis[i]` 是 `PauliI` 或 `PauliZ` ，則為 $p _i = $1 `paulis[i]` `PauliX` `PauliY` 。

## <a name="remarks"></a>備註

如果陣列的長度大於63，函數將會擲回 `paulis` 。

## <a name="see-also"></a>另請參閱

- [ZBits。](xref:Microsoft.Quantum.Bitwise.ZBits)