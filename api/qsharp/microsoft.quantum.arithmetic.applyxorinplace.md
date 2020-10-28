---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699958"
---
# <a name="applyxorinplace-operation"></a>ApplyXorInPlace 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


在傳統整數與量子位暫存器所代表的整數之間套用位 XOR 運算。

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>描述

`X`根據整數中的1位，將作業套用至以小到小的暫存器量子位。

讓我們 `value` 用來表示，並讓 y 成為以不帶正負號的整數編碼 `target` ，然後 `InPlaceXorLE` 執行下列對應所提供的作業： $ \ket{y}\rightarrow \ket{y\oplus a} $，其中 $ \oplus $ 是位互斥 OR 運算子。

## <a name="input"></a>輸入

### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

假設為非負數的整數。


### <a name="target--littleendian"></a>目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

用來儲存以位元組由小到大編碼的量子暫存器 `value` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

