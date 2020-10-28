---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699902"
---
# <a name="computereciprocali-operation"></a>ComputeReciprocalI 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


使用整數除法計算不帶正負號整數 x 的倒數 1/x。 結果（以整數來解讀）將會是 `floor(2^(2*n-1) / x)` 。

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

n 位不帶正負號整數


### <a name="result--littleendian"></a>結果： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

2n 位輸出的初始必須是 $ \ket {0} $。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

針對輸入 x = 0，輸出將會是所有的輸出。