---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848353"
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



## <a name="example"></a>範例

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a>備註

此函式會藉由包裝單元圓圈相關的實數來計算實際模數，然後尋找對應于輸入的單位圓形上的角度。
`minValue`然後，輸入會有效地指定要將單元圓形剪下的位置。