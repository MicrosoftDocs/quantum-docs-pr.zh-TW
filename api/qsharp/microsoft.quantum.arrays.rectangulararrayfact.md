---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699430"
---
# <a name="rectangulararrayfact-function"></a>RectangularArrayFact 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


表示二維陣列具有矩形形狀的條件

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>描述

此函式會判斷陣列中的每個資料列都具有相同的長度。

## <a name="input"></a>輸入

### <a name="array--t"></a>陣列： t [] []

二維元素陣列


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

如果陣列不是矩形陣列，要列印的訊息



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

之每個專案的型別 `array` 。

## <a name="see-also"></a>另請參閱

- [SquareArrayFact。](xref:Microsoft.Quantum.Arrays.SquareArrayFact)