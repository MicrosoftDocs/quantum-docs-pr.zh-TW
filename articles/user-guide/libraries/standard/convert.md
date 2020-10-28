---
title: '標準程式庫中的類型轉換 :::no-loc(Q#):::'
description: '瞭解標準程式庫中的一般和使用者定義型別轉換函式 :::no-loc(Q#)::: 。'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 9ec3a2ecd2aa59a10a7033e7b3067eb147ce4035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691109"
---
# <a name="type-conversions"></a><span data-ttu-id="3da8a-103">類型轉換</span><span class="sxs-lookup"><span data-stu-id="3da8a-103">Type Conversions</span></span> #

<span data-ttu-id="3da8a-104">:::no-loc(Q#)::: 是 **強型** 別語言。</span><span class="sxs-lookup"><span data-stu-id="3da8a-104">:::no-loc(Q#)::: is a **strongly-typed** language.</span></span>
<span data-ttu-id="3da8a-105">特別的是，不 :::no-loc(Q#)::: 會在相異類型之間隱含轉換。</span><span class="sxs-lookup"><span data-stu-id="3da8a-105">In particular, :::no-loc(Q#)::: does not implicitly cast between distinct types.</span></span> <span data-ttu-id="3da8a-106">例如，不是 `1 + 2.0` 有效的 :::no-loc(Q#)::: 運算式。</span><span class="sxs-lookup"><span data-stu-id="3da8a-106">For instance, `1 + 2.0` is not a valid :::no-loc(Q#)::: expression.</span></span>
<span data-ttu-id="3da8a-107">相反地，會 :::no-loc(Q#)::: 提供各種類型轉換函式來建立特定類型的新值。</span><span class="sxs-lookup"><span data-stu-id="3da8a-107">Rather, :::no-loc(Q#)::: provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="3da8a-108">例如， <xref:Microsoft.Quantum.Core.Length> 具有的輸出型別 `Int` ，因此它的輸出必須先轉換成，然後才能當做 `Double` 浮點運算式的一部分使用。</span><span class="sxs-lookup"><span data-stu-id="3da8a-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="3da8a-109">您可以使用函數來完成此動作 <xref:Microsoft.Quantum.Convert.IntAsDouble> ：</span><span class="sxs-lookup"><span data-stu-id="3da8a-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="3da8a-110"><xref:Microsoft.Quantum.Convert>命名空間提供一般的型別轉換函式，可處理基本的內建類型，例如 `Int` 、、 `Double` `BigInt` 、 `Result` 和 `Bool` ：</span><span class="sxs-lookup"><span data-stu-id="3da8a-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="3da8a-111"><xref:Microsoft.Quantum.Convert>命名空間也會提供一些更外來的轉換，例如將函式轉換 `FunctionAsOperation` `'T -> 'U` 成新作業的 `'T => 'U` 。</span><span class="sxs-lookup"><span data-stu-id="3da8a-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="3da8a-112">最後， :::no-loc(Q#)::: 標準程式庫會提供一些使用者定義類型，例如 <xref:Microsoft.Quantum.Math.Complex> 和 <xref:Microsoft.Quantum.Arithmetic.LittleEndian> 。</span><span class="sxs-lookup"><span data-stu-id="3da8a-112">Finally, the :::no-loc(Q#)::: standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="3da8a-113">除了這些類型，標準程式庫還提供 <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> 下列功能：</span><span class="sxs-lookup"><span data-stu-id="3da8a-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```:::no-loc(Q#):::
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
