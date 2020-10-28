---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: c60c2827060f4ef223ebaf80ccdef09faaf56098
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699922"
---
# <a name="comparegti-operation"></a>CompareGTI 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


整數比較的包裝函式： `result = x > y` 。

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

第一個 $n $ 位數位


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

第二 $n $ 位數位


### <a name="result--qubit"></a>結果： [量子位](xref:microsoft.quantum.lang-ref.qubit)

如果 $x > y $，將會翻轉



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

