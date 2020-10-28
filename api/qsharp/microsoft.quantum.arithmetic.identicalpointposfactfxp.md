---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699866"
---
# <a name="identicalpointposfactfxp-function"></a>IdenticalPointPosFactFxP 函式

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


判斷出所提供陣列中的所有固定點數位在從最小的位元數目時，都有相同的點位置。 亦即，陣列中所有固定點數位的位數減去點位置的位數必須是常數。

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a>輸入

### <a name="fixedpoints--fixedpoint"></a>fixedPoints： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]

將會使用判斷提示) 檢查相容性 (的量子固定點數位陣列。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

