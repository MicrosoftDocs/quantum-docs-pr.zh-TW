---
title: 'Q # 標準程式庫中的類型轉換'
description: '瞭解 Q # 標準程式庫中的一般和使用者定義類型轉換函式。'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907795"
---
# <a name="type-conversions"></a>類型轉換 #

問 # 是**強型**別語言。
特別的是，Q # 並不會在相異類型之間隱含轉換。 例如，`1 + 2.0` 不是有效的 Q # 運算式。
相反地，Q # 提供各種類型轉換函式來建立指定類型的新值。

例如，<xref:microsoft.quantum.core.length> 具有 `Int`的輸出類型，因此它的輸出必須先轉換成 `Double`，才能當做浮點運算式的一部分使用。
這可以使用 <xref:microsoft.quantum.convert.intasdouble> 函數來完成：

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:microsoft.quantum.convert> 命名空間提供一般類型轉換函式，以使用基本內建類型，例如 `Int`、`Double`、`BigInt`、`Result`和 `Bool`：

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:microsoft.quantum.convert> 命名空間也會提供一些更外來的轉換，例如 `FunctionAsOperation`，這會將函式 `'T -> 'U` 轉換成新的作業 `'T => 'U`。

最後，Q # 標準程式庫提供許多使用者定義的類型，例如 <xref:microsoft.quantum.math.complex> 和 <xref:microsoft.quantum.arithmetic.littleendian>。
除了這些類型，標準程式庫還提供如 <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>的功能：

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
