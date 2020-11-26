---
uid: Microsoft.Quantum.Math.Fraction
title: 分數使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210670"
---
# <a name="fraction-user-defined-type"></a>分數使用者定義型別

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示表單的有理數 `p/q` 。 整數 `p` 是元組的第一個元素，而 `q` 是元組的第二個元素。

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>命名專案

### <a name="numerator--int"></a>分子： [Int](xref:microsoft.quantum.lang-ref.int)

分數的分子。
### <a name="denominator--int"></a>分母： [Int](xref:microsoft.quantum.lang-ref.int)

分數/的分母