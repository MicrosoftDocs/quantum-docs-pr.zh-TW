---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699677"
---
# <a name="realmod-function"></a>RealMod 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

包： [](https://nuget.org/packages/)


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