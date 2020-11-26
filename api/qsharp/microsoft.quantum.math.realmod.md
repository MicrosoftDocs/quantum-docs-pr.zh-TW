---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228248"
---
# <a name="realmod-function"></a>RealMod 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


計算兩個實數之間的模數。

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a>輸入

### <a name="value--double"></a>值： [Double](xref:microsoft.quantum.lang-ref.double)

$X $ 取得模數的實數。


### <a name="modulo--double"></a>模數： [Double](xref:microsoft.quantum.lang-ref.double)

要採用 $x $ 的模數的實際數位。


### <a name="minvalue--double"></a>minValue： [Double](xref:microsoft.quantum.lang-ref.double)

此函數所傳回的最小值。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>備註

此函式會藉由包裝單元圓圈相關的實數來計算實際模數，然後尋找對應于輸入的單位圓形上的角度。
`minValue`然後，輸入會有效地指定要將單元圓形剪下的位置。