---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699519"
---
# <a name="columnat-function"></a>ColumnAt 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


從矩陣中解壓縮資料行。

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>描述

此函式會以資料列的順序來解壓縮矩陣中的資料行。
將資料列 corrsponds 解壓縮至第一個索引的專案存取，因此不需要進一步處理。

## <a name="input"></a>輸入

### <a name="column--int"></a>資料行： [Int](xref:microsoft.quantum.lang-ref.int)

矩陣的資料行


### <a name="matrix--t"></a>矩陣： t [] []

以資料列順序排列的二維矩陣



## <a name="output--t"></a>Output： t []



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

之每個專案的型別 `matrix` 。

## <a name="see-also"></a>另請參閱

- [（.......。](xref:Microsoft.Quantum.Arrays.Transposed)
- [Node.js. 對角線](xref:Microsoft.Quantum.Arrays.Diagonal)