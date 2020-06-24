---
title: 'Q # 標準程式庫中的類型轉換'
description: '瞭解 Q # 標準程式庫中的一般和使用者定義類型轉換函式。'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274615"
---
# <a name="type-conversions"></a><span data-ttu-id="b71fa-103">類型轉換</span><span class="sxs-lookup"><span data-stu-id="b71fa-103">Type Conversions</span></span> #

<span data-ttu-id="b71fa-104">問 # 是**強型**別語言。</span><span class="sxs-lookup"><span data-stu-id="b71fa-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="b71fa-105">特別的是，Q # 並不會在相異類型之間隱含轉換。</span><span class="sxs-lookup"><span data-stu-id="b71fa-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="b71fa-106">例如，不是 `1 + 2.0` 有效的 Q # 運算式。</span><span class="sxs-lookup"><span data-stu-id="b71fa-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="b71fa-107">相反地，Q # 提供各種類型轉換函式來建立指定類型的新值。</span><span class="sxs-lookup"><span data-stu-id="b71fa-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="b71fa-108">例如，的 <xref:microsoft.quantum.core.length> 輸出類型為 `Int` ，因此它的輸出必須先轉換成，然後才能當做 `Double` 浮點運算式的一部分使用。</span><span class="sxs-lookup"><span data-stu-id="b71fa-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="b71fa-109">這可以使用函數來完成 <xref:microsoft.quantum.convert.intasdouble> ：</span><span class="sxs-lookup"><span data-stu-id="b71fa-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="b71fa-110"><xref:microsoft.quantum.convert>命名空間提供一般類型轉換函式，以使用基本內建類型，例如 `Int` 、 `Double` 、 `BigInt` 、 `Result` 和 `Bool` ：</span><span class="sxs-lookup"><span data-stu-id="b71fa-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="b71fa-111"><xref:microsoft.quantum.convert>命名空間也會提供一些更外來的轉換（例如 `FunctionAsOperation` ），以將函式轉換 `'T -> 'U` 成新的作業 `'T => 'U` 。</span><span class="sxs-lookup"><span data-stu-id="b71fa-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="b71fa-112">最後，Q # 標準程式庫提供許多使用者定義的類型，例如 <xref:microsoft.quantum.math.complex> 和 <xref:microsoft.quantum.arithmetic.littleendian> 。</span><span class="sxs-lookup"><span data-stu-id="b71fa-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="b71fa-113">除了這些類型，標準程式庫還提供 <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> 下列功能：</span><span class="sxs-lookup"><span data-stu-id="b71fa-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
