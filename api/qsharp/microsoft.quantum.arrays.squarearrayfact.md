---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: 3529718f0c903266d21fd593c11c0149dae0fa2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220190"
---
# <a name="squarearrayfact-function"></a>SquareArrayFact 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示二維陣列具有方形形狀的條件

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>描述

此函式會判斷陣列中的每個資料列都有相同數目的元素，因為陣列中的資料列 (元素) 。

## <a name="input"></a>輸入

### <a name="array--t"></a>陣列： t [] []

二維元素陣列


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

如果陣列不是正方形陣列，要列印的訊息



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

之每個專案的型別 `array` 。

## <a name="see-also"></a>另請參閱

- [RectangularArrayFact。](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)