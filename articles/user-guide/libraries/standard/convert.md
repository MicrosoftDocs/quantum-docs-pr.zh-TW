---
title: 標準程式庫中的類型轉換 Q#
description: 瞭解標準程式庫中的通用和使用者定義類型轉換函式 Q# 。
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2319bf453f5fbf6bd068859ea65562423d3ff4d0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868504"
---
# <a name="type-conversions"></a>類型轉換 #

Q#是**強型**別語言。
特別的是，不 Q# 會在相異類型之間隱含轉換。 例如，不是 `1 + 2.0` 有效的 Q# 運算式。
而是 Q# 提供各種類型轉換函式，以供您用來建立指定類型的新值。

例如，的 <xref:microsoft.quantum.core.length> 輸出類型為 `Int` ，因此它的輸出必須先轉換成，然後才能當做 `Double` 浮點運算式的一部分使用。
這可以使用函數來完成 <xref:microsoft.quantum.convert.intasdouble> ：

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:microsoft.quantum.convert>命名空間提供一般類型轉換函式，以使用基本內建類型，例如 `Int` 、 `Double` 、 `BigInt` 、 `Result` 和 `Bool` ：

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:microsoft.quantum.convert>命名空間也會提供一些更外來的轉換（例如 `FunctionAsOperation` ），以將函式轉換 `'T -> 'U` 成新的作業 `'T => 'U` 。

最後， Q# 標準程式庫提供許多使用者定義的類型，例如 <xref:microsoft.quantum.math.complex> 和 <xref:microsoft.quantum.arithmetic.littleendian> 。
除了這些類型，標準程式庫還提供 <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> 下列功能：

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
