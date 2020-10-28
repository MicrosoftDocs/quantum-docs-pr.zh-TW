---
uid: Microsoft.Quantum.Arrays.Transposed
title: 已轉換函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699412"
---
# <a name="transposed-function"></a>已轉換函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


傳回表示為數組陣列的矩陣的調換。

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>描述

以 $r \times c $ 矩陣的形式輸入 $r $ rows 和 $c $ columns。  矩陣是以資料列為基礎，也就是 `matrix[i][j]` 存取資料列 $i $ 和 column $j $ 的元素。

此函式會傳回 $c \times r $ matrix，這是輸入矩陣的換位。

## <a name="input"></a>輸入

### <a name="matrix--t"></a>矩陣： t [] []

以資料列為基礎的 $r \times c $ matrix



## <a name="output--t"></a>Output： t [] []

已轉換 $c \times r $ matrix

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

之每個專案的型別 `matrix` 。