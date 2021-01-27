---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843113"
---
# <a name="measureinteger-operation"></a>MeasureInteger 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


測量量子暫存器的內容，並將它轉換成整數。 測量是以標準計算為基礎來執行，亦即，的 eigenbasis `PauliZ` 。

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>輸入

### <a name="target--littleendian"></a>目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

以位元組由大到小的編碼方式的量子暫存器。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

不帶正負號的整數，其中包含的測量值 `target` 。

## <a name="remarks"></a>備註

此作業會將其輸入暫存器重設為 $ \ket{00\cdots 0} $ 狀態，適合用來釋回目的電腦。

## <a name="see-also"></a>另請參閱

- [Canon. MeasureIntegerBE](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)