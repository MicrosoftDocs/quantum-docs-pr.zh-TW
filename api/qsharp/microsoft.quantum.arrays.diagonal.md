---
uid: Microsoft.Quantum.Arrays.Diagonal
title: 對角函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221533"
---
# <a name="diagonal-function"></a>對角函數

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回二維陣列的對角線元素陣列

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>描述

如果二維陣列沒有方形圖形，則會傳回資料列和資料行數目最小值的對角線。

## <a name="input"></a>輸入

### <a name="matrix--t"></a>矩陣： t [] []

以資料列順序排列的二維矩陣



## <a name="output--t"></a>Output： t []



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

之每個專案的型別 `matrix` 。

## <a name="see-also"></a>另請參閱

- [（.......。](xref:Microsoft.Quantum.Arrays.Transposed)