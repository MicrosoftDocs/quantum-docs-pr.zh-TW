---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197579"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison 函式

命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定比較函式時，會傳回 lexographically 比較兩個數組的新函數。

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a>輸入

### <a name="elementcomparison--tt---bool"></a>elementComparison： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

比較兩個元素的函式， `x` `y` 如果 `x` 小於或等於，則傳回 `y` 。



## <a name="output--tt---bool"></a>Output： ( t []，t [] ) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

比較兩個數組的函式， `xs` `ys` 如果 `xs` 發生在 lexographical 順序之前或等於，則會傳回 `ys` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要比較之陣列的元素類型。

## <a name="remarks"></a>備註

兩個數組之間的 lexographic `xs` 比較 `ys` 會由下列程式定義。 `x` `y` 如果 `elementComparison(x, y)` 和 `elementComparison(y, x)` 都是 true，就表示兩個元素和相等。

- 這兩個數組都是依元素進行比較，直到第一對不相等的元素為止。 在 lexographical 順序中，第一個會根據所發生的元素，包含最先發生的專案 `elementComparison` 。
- 如果找不到任何 inequivalent 元素，且其中一個陣列的長度超過另一個陣列，則會先將較短的陣列視為發生。

## <a name="see-also"></a>另請參閱

- [依序排序的](xref:Microsoft.Quantum.Arrays.Sorted)