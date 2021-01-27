---
title: 標準程式庫中的類型轉換 Q#
description: 瞭解標準程式庫中的一般和使用者定義型別轉換函式 Q# 。
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: 67f47339363a52097f342c8ae4e43a8a93d606a8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858031"
---
# <a name="type-conversions"></a>類型轉換 #

Q# 是 **強型** 別語言。
特別的是，不 Q# 會在相異類型之間隱含轉換。 例如，不是 `1 + 2.0` 有效的 Q# 運算式。
相反地，會 Q# 提供各種類型轉換函式來建立特定類型的新值。

例如， <xref:Microsoft.Quantum.Core.Length> 具有的輸出型別 `Int` ，因此它的輸出必須先轉換成，然後才能當做 `Double` 浮點運算式的一部分使用。
您可以使用函數來完成此動作 <xref:Microsoft.Quantum.Convert.IntAsDouble> ：

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:Microsoft.Quantum.Convert>命名空間提供一般的型別轉換函式，可處理基本的內建類型，例如 `Int` 、、 `Double` `BigInt` 、 `Result` 和 `Bool` ：

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:Microsoft.Quantum.Convert>命名空間也會提供一些更外來的轉換，例如將函式轉換 `FunctionAsOperation` `'T -> 'U` 成新作業的 `'T => 'U` 。

最後， Q# 標準程式庫會提供一些使用者定義類型，例如 <xref:Microsoft.Quantum.Math.Complex> 和 <xref:Microsoft.Quantum.Arithmetic.LittleEndian> 。
除了這些類型，標準程式庫還提供 <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> 下列功能：

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
