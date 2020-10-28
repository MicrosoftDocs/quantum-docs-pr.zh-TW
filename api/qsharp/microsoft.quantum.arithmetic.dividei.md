---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699899"
---
# <a name="dividei-operation"></a>DivideI 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


將兩個量子整數相除。

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>描述

`xs` 將保留其餘部分 `xs - floor(xs/ys) * ys` ，並 `result` 將保留 `floor(xs/ys)` 。

## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ 位被除數，將被餘數取代。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ bit 除數


### <a name="result--littleendian"></a>結果： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ bit 結果時，必須先處於狀態 $ \ket {0} $，並且將由整數除法的結果取代。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

使用標準的 shift 和減法方法來執行除法。
受控制的版本是特製化的，因此減法不需要額外的控制項。