---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222417"
---
# <a name="phaselittleendian-user-defined-type"></a>PhaseLittleEndian 使用者定義型別

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


以 QFT 為基礎的位元組由小到大不帶正負號的整數。

例如，如果 $ \ket{x} $ 是整數 $x $ 的位元組由大到小編碼，則 $ \operatorname{QFTLE} \ket{x} $ 是 QFT 基礎中 $x $ 的編碼方式。

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a>備註

我們 `PhaseLittleEndian` `PhaseLE` 將在檔中縮寫。

## <a name="see-also"></a>另請參閱

- [Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)
- [Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)