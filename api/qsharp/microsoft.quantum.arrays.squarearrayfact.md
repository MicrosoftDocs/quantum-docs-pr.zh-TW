---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699419"
---
# <a name="squarearrayfact-function"></a>SquareArrayFact 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


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