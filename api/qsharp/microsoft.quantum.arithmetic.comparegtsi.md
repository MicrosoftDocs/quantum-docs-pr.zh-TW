---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699919"
---
# <a name="comparegtsi-operation"></a>CompareGTSI 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


帶正負號整數比較的包裝函式： `result = xs > ys` 。

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="xs--signedlittleendian"></a>xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

第一個 $n $ 位數位


### <a name="ys--signedlittleendian"></a>y) ： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

第二 $n $ 位數位


### <a name="result--qubit"></a>結果： [量子位](xref:microsoft.quantum.lang-ref.qubit)

如果 $xs > y) $，將會翻轉



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

