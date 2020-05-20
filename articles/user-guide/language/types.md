---
title: Q# 中的類型
description: '瞭解問答 # 程式設計語言中使用的不同類型。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 4a551ee90a0abb6e42953cf04c7f5a8ca3573f26
ms.sourcegitcommit: 682a4a5f5dd23ca58a4addf62aea4086bb308552
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609136"
---
# <a name="types-in-q"></a><span data-ttu-id="e3c13-103">Q# 中的類型</span><span class="sxs-lookup"><span data-stu-id="e3c13-103">Types in Q#</span></span>

<span data-ttu-id="e3c13-104">此頁面會配置 Q # 類型模型，並描述用於指定和使用類型的語法。</span><span class="sxs-lookup"><span data-stu-id="e3c13-104">This page lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="e3c13-105">下一個頁面 [[類型運算式](xref:microsoft.quantum.guide.expressions)] 會詳細說明如何建立和操作這些類型的運算式。</span><span class="sxs-lookup"><span data-stu-id="e3c13-105">The next page, [Type Expressions](xref:microsoft.quantum.guide.expressions), details how to create and operate on expressions of these types.</span></span>

<span data-ttu-id="e3c13-106">我們注意到，Q # 是*強型*別語言，因此小心使用這些型別可協助編譯器在編譯時期提供有關 Q # 程式的強式保證。</span><span class="sxs-lookup"><span data-stu-id="e3c13-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="e3c13-107">為了提供最強的保證，在 Q # 中類型之間的轉換必須使用表達該轉換的函式呼叫來明確地進行。</span><span class="sxs-lookup"><span data-stu-id="e3c13-107">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="e3c13-108">在命名空間中提供各種不同的函式 <xref:microsoft.quantum.convert> 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-108">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="e3c13-109">另一方面，Upcasts 到相容的型別就會隱含地發生。</span><span class="sxs-lookup"><span data-stu-id="e3c13-109">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="e3c13-110">Q # 同時提供兩種基本類型，可以直接使用，以及從其他類型產生新類型的各種方式。</span><span class="sxs-lookup"><span data-stu-id="e3c13-110">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="e3c13-111">我們會在本節的其餘部分說明每個。</span><span class="sxs-lookup"><span data-stu-id="e3c13-111">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="e3c13-112">基本類型</span><span class="sxs-lookup"><span data-stu-id="e3c13-112">Primitive Types</span></span>

<span data-ttu-id="e3c13-113">Q # 語言提供了數種*基本類型*，可從中建造其他類型：</span><span class="sxs-lookup"><span data-stu-id="e3c13-113">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="e3c13-114">`Int`型別代表64位帶正負號的整數，例如： `2` 、 `107` 、 `-5` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-114">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="e3c13-115">`BigInt`類型代表任意大小的帶正負號整數，例如、 `2L` `107L` 、 `-5L` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-115">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="e3c13-116">此類型是以 .NET 為基礎<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="e3c13-116">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="e3c13-117">型.</span><span class="sxs-lookup"><span data-stu-id="e3c13-117">type.</span></span>
- <span data-ttu-id="e3c13-118">`Double`型別代表雙精確度浮點數，例如： `0.0` 、 `-1.3` 、 `4e-7` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-118">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="e3c13-119">此 `Bool` 類型代表布林值，可以是 `true` 或 `false` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-119">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="e3c13-120">`Range`型別代表一連串的整數，以表示 `start..step..stop` 步驟是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="e3c13-120">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="e3c13-121">這會 `start .. stop` 對應至 `start..1..stop` ，例如 `1..2..7` 代表序列 $ \{ 1、3、5、7 \} $。</span><span class="sxs-lookup"><span data-stu-id="e3c13-121">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="e3c13-122">`String`類型是一系列的 Unicode 字元，不是使用者建立後的不透明。</span><span class="sxs-lookup"><span data-stu-id="e3c13-122">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="e3c13-123">此類型是用來在發生錯誤或診斷事件時，將訊息報告給傳統主機。</span><span class="sxs-lookup"><span data-stu-id="e3c13-123">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="e3c13-124">`Unit`類型是只允許一個值的類型 `()` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-124">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="e3c13-125">這個類型是用來表示 Q # 函式或作業不會傳回任何資訊。</span><span class="sxs-lookup"><span data-stu-id="e3c13-125">This type is used to indicate that Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="e3c13-126">`Qubit`型別代表量子位或 qubit。</span><span class="sxs-lookup"><span data-stu-id="e3c13-126">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="e3c13-127">`Qubit`對使用者而言，是不透明的;除了將它們傳遞至另一個作業以外，唯一可行的作業是測試身分識別（相等）。</span><span class="sxs-lookup"><span data-stu-id="e3c13-127">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="e3c13-128">最後，的動作 `Qubit` 是藉由呼叫量子處理器上的內建指示來執行（或模擬）。</span><span class="sxs-lookup"><span data-stu-id="e3c13-128">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="e3c13-129">`Pauli`類型代表四個單一 Qubit Pauli 運算子的其中一個。</span><span class="sxs-lookup"><span data-stu-id="e3c13-129">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="e3c13-130">這個型別是用來表示旋轉的基底作業，並指定要測量的可觀察。</span><span class="sxs-lookup"><span data-stu-id="e3c13-130">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="e3c13-131">這是列舉型別，其中包含四個可能 `PauliI` 的值：、 `PauliX` 、 `PauliY` 和 `PauliZ` ，這是類型的常數 `Pauli` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-131">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="e3c13-132">`Result`型別代表測量結果。</span><span class="sxs-lookup"><span data-stu-id="e3c13-132">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="e3c13-133">這是具有兩個可能值的列舉類型： `One` 和 `Zero` ，它們是類型的常數 `Result` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-133">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="e3c13-134">`Zero`表示已測量 + 1 eigenvalue;`One`表示-1 eigenvalue。</span><span class="sxs-lookup"><span data-stu-id="e3c13-134">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>

<span data-ttu-id="e3c13-135">常數 `true` 、、、、、、 `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` 和 `Zero` 都是 Q # 中的所有保留符號。</span><span class="sxs-lookup"><span data-stu-id="e3c13-135">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="e3c13-136">陣列類型</span><span class="sxs-lookup"><span data-stu-id="e3c13-136">Array Types</span></span>

<span data-ttu-id="e3c13-137">假設有任何有效的 Q # 類型 `'T` ，則會有代表類型值陣列的類型 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-137">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="e3c13-138">這個陣列型別會表示為 `'T[]` ; 例如， `Qubit[]` 或 `Int[][]` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-138">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="e3c13-139">例如，整數的集合是以表示 `Int[]` ，而值陣列的陣列 `(Bool, Pauli)` 則是表示 `(Bool, Pauli)[][]` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-139">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="e3c13-140">在第二個範例中，請注意這代表可能不規則的陣列陣列，而不是矩形二維陣列。</span><span class="sxs-lookup"><span data-stu-id="e3c13-140">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="e3c13-141">問 # 不提供對矩形多維陣列的支援。</span><span class="sxs-lookup"><span data-stu-id="e3c13-141">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="e3c13-142">您可以使用方括弧括住陣列的元素，將陣列值寫入至 Q # 原始程式碼中，如中所示 `[PauliI, PauliX, PauliY, PauliZ]` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-142">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="e3c13-143">陣列常值的類型取決於陣列中所有專案的通用基底類型。</span><span class="sxs-lookup"><span data-stu-id="e3c13-143">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="e3c13-144">建立陣列之後，就無法變更陣列的元素。</span><span class="sxs-lookup"><span data-stu-id="e3c13-144">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="e3c13-145">[Update-重新指派語句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)和（或）[複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)可以用來建立已修改的陣列。</span><span class="sxs-lookup"><span data-stu-id="e3c13-145">[Update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) and/or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) can be used to construct a modified array.</span></span>

<span data-ttu-id="e3c13-146">或者，您可以使用關鍵字，從其大小建立陣列 `new` ：</span><span class="sxs-lookup"><span data-stu-id="e3c13-146">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="e3c13-147">不論是哪一種情況，一旦結構化陣列之後， `Length` 就可以使用核心函式來取得專案的數目 `Int` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-147">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="e3c13-148">陣列可以使用方括弧（具有類型或類型的注標）來做為下標 `Int` `Range` ，以取得單一專案或包含陣列元素子集的新陣列。</span><span class="sxs-lookup"><span data-stu-id="e3c13-148">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="e3c13-149">陣列的注標是以零為基底：</span><span class="sxs-lookup"><span data-stu-id="e3c13-149">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="e3c13-150">元組類型</span><span class="sxs-lookup"><span data-stu-id="e3c13-150">Tuple Types</span></span>

<span data-ttu-id="e3c13-151">假設有零或多個不同的類型 `T0` ， `T1` ，...， `Tn` 我們可以將新的*元組類型*表示為 `(T0, T1, ..., Tn)` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-151">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="e3c13-152">用來建立新元組類型的類型本身可以是元組，如中所示 `(Int, (Qubit, Qubit))` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-152">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="e3c13-153">不過，這類的嵌套一定是有限的，因為在任何情況下，元組類型不能包含本身。</span><span class="sxs-lookup"><span data-stu-id="e3c13-153">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="e3c13-154">新元組類型的值是由元組中每個類型的值序列所組成的元組。</span><span class="sxs-lookup"><span data-stu-id="e3c13-154">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="e3c13-155">例如， `(3, false)` 是其類型為元組類型的元組 `(Int, Bool)` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-155">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="e3c13-156">您可以建立元組的陣列、陣列的元組、子元組的元組等等。</span><span class="sxs-lookup"><span data-stu-id="e3c13-156">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="e3c13-157">從 Q # 0.3， `Unit` 是空元組的*型*別名稱， `()` 用於空的元組*值*。</span><span class="sxs-lookup"><span data-stu-id="e3c13-157">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="e3c13-158">元組實例為不可變。</span><span class="sxs-lookup"><span data-stu-id="e3c13-158">Tuple instances are immutable.</span></span>
<span data-ttu-id="e3c13-159">問 # 未提供在建立後變更元組內容的機制。</span><span class="sxs-lookup"><span data-stu-id="e3c13-159">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="e3c13-160">元組是一種功能強大的概念，用於整個 Q #，將值一起收集成單一值，使其更容易傳遞。</span><span class="sxs-lookup"><span data-stu-id="e3c13-160">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="e3c13-161">特別是，使用元組標記法時，我們可以表示每個作業和可呼叫都只接受一個輸入，而且只會傳回一個輸出。</span><span class="sxs-lookup"><span data-stu-id="e3c13-161">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="e3c13-162">單一元組等價</span><span class="sxs-lookup"><span data-stu-id="e3c13-162">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="e3c13-163">您可以建立單一（單一元素）元組， `('T1)` 例如 `(5)` 或 `([1,2,3])` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-163">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="e3c13-164">不過，Q # 會將單一元組視為完全等同于已括住類型的值。</span><span class="sxs-lookup"><span data-stu-id="e3c13-164">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="e3c13-165">也就是說，和之間沒有任何差異，或介於和之間 `5` `(5)` `5` `(((5)))` ，或介於 `(5, (6))` 和之間 `(5, 6)` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-165">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="e3c13-166">這就是寫入 `(5)+3` 為寫入的有效值 `5+3` ，而且這兩個運算式會評估為 `8` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>

<span data-ttu-id="e3c13-167">此等價適用于所有用途，包括指派和運算式。</span><span class="sxs-lookup"><span data-stu-id="e3c13-167">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="e3c13-168">假設有任何運算式，以括弧括住的相同運算式就是相同類型的運算式。</span><span class="sxs-lookup"><span data-stu-id="e3c13-168">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="e3c13-169">例如， `(7)` 是 `Int` 運算式， `([1,2,3])` 是 s 類型的運算式 `Int` ，而是型別為的 `((1,2))` 運算式 `(Int, Int)` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-169">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="e3c13-170">特別是，這表示輸入元組或輸出元組類型具有一個欄位的作業或函數，可以視為接受單一引數或傳回單一值。</span><span class="sxs-lookup"><span data-stu-id="e3c13-170">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="e3c13-171">我們將此屬性稱為_單一元組等價_。</span><span class="sxs-lookup"><span data-stu-id="e3c13-171">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="e3c13-172">使用者定義類型</span><span class="sxs-lookup"><span data-stu-id="e3c13-172">User-Defined Types</span></span>

<span data-ttu-id="e3c13-173">使用者定義型別宣告包含關鍵字 `newtype` ，後面接著使用者定義型別的名稱、 `=` 、有效的型別規格，以及終止的分號。</span><span class="sxs-lookup"><span data-stu-id="e3c13-173">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="e3c13-174">例如：</span><span class="sxs-lookup"><span data-stu-id="e3c13-174">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="e3c13-175">每個 Q # 來源檔案都可以宣告任何數目的使用者定義類型。</span><span class="sxs-lookup"><span data-stu-id="e3c13-175">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="e3c13-176">類型名稱在命名空間中必須是唯一的，而且可能不會與作業和函式名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="e3c13-176">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="e3c13-177">即使基底類型完全相同，使用者定義類型也是相異的。</span><span class="sxs-lookup"><span data-stu-id="e3c13-177">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="e3c13-178">特別是，兩個使用者自訂類型的值之間不會自動轉換，即使基礎類型相同也一樣。</span><span class="sxs-lookup"><span data-stu-id="e3c13-178">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="e3c13-179">名稱與匿名專案的比較</span><span class="sxs-lookup"><span data-stu-id="e3c13-179">Named vs. anonymous items</span></span>

<span data-ttu-id="e3c13-180">Q # 檔案可能會定義新的命名類型，其中包含任何合法類型的單一值。</span><span class="sxs-lookup"><span data-stu-id="e3c13-180">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="e3c13-181">針對任何元組類型 `T` ，我們可以宣告新的使用者自訂類型，這是具有語句的子類型 `T` `newtype` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-181">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="e3c13-182">例如，在 @"microsoft.quantum.math" 命名空間中，複數會定義為使用者定義型別：</span><span class="sxs-lookup"><span data-stu-id="e3c13-182">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="e3c13-183">這個語句會建立具有兩個型別之匿名專案的新型別 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-183">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="e3c13-184">除了匿名專案以外，使用者定義型別也支援從 Q # 0.7 版或更高版本開始的*命名專案*。</span><span class="sxs-lookup"><span data-stu-id="e3c13-184">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="e3c13-185">例如，我們可以將 `Re` 代表複數實數部分之 double 的專案命名為，並 `Im` 為虛數部分指定：</span><span class="sxs-lookup"><span data-stu-id="e3c13-185">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="e3c13-186">將使用者定義型別中的一個專案命名，並不表示所有專案都必須命名，而且支援任何組合的已命名和未命名專案。</span><span class="sxs-lookup"><span data-stu-id="e3c13-186">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="e3c13-187">此外，內部專案也可以命名為。</span><span class="sxs-lookup"><span data-stu-id="e3c13-187">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="e3c13-188">例如， `Nested` 下列定義的類型具有基礎類型 `(Double, (Int, String))` ，其中只有類型的專案 `Int` 會命名為，而所有其他專案則為匿名。</span><span class="sxs-lookup"><span data-stu-id="e3c13-188">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="e3c13-189">命名專案的優點是可以透過*存取運算子*直接存取它們 `::` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-189">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="e3c13-190">除了為可能複雜的元組類型提供簡短的別名之外，定義這類類型的其中一個重要優點是，它們可以記錄特定值的意圖。</span><span class="sxs-lookup"><span data-stu-id="e3c13-190">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="e3c13-191">回到的範例 `Complex` ，其中一個也可以定義2d 極座標做為使用者定義的型別：</span><span class="sxs-lookup"><span data-stu-id="e3c13-191">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="e3c13-192">雖然和都 `Complex` `Polar` 具有基礎類型，但這 `(Double, Double)` 兩個類型在 Q # 中完全不相容，因此不小心以極座標呼叫複雜數學函式的風險降至最低，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="e3c13-192">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="e3c13-193">如此一來，使用者定義型別與 F # 中的記錄具有類似的角色，例如。</span><span class="sxs-lookup"><span data-stu-id="e3c13-193">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="e3c13-194">使用解除包裝運算子來存取匿名專案</span><span class="sxs-lookup"><span data-stu-id="e3c13-194">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="e3c13-195">若要存取另一方面的匿名專案，必須使用後置運算子來解壓縮已包裝的值 `!` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-195">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="e3c13-196">「解除包裝」運算子 `!` 可讓將使用者定義型別中包含的值解壓縮。</span><span class="sxs-lookup"><span data-stu-id="e3c13-196">The "unwrap" operator, `!`, allows to extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="e3c13-197">這類「解除包裝」運算式的類型是使用者定義類型的基礎類型。</span><span class="sxs-lookup"><span data-stu-id="e3c13-197">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="e3c13-198">解除包裝運算子只會解除封裝一層換行。</span><span class="sxs-lookup"><span data-stu-id="e3c13-198">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="e3c13-199">可以使用多個解除包裝運算子來存取已相乘的值。</span><span class="sxs-lookup"><span data-stu-id="e3c13-199">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="e3c13-200">例如：</span><span class="sxs-lookup"><span data-stu-id="e3c13-200">For instance:</span></span>

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

<span data-ttu-id="e3c13-201">如需解除包裝運算子的詳細資訊，請參閱[Q # 中的類型運算式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="e3c13-201">More details on the unwrap operator can be found at [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="e3c13-202">建立使用者自訂類型的值</span><span class="sxs-lookup"><span data-stu-id="e3c13-202">Creating values of user-defined types</span></span>

<span data-ttu-id="e3c13-203">使用者自訂類型的值可以藉由呼叫對應的類型的函式來建立：</span><span class="sxs-lookup"><span data-stu-id="e3c13-203">Values of a user-defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="e3c13-204">或者，您可以使用[複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)，從現有的值建立新的值。</span><span class="sxs-lookup"><span data-stu-id="e3c13-204">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="e3c13-205">如同陣列，這類運算式會複製原始運算式的所有專案值，但指定的命名專案除外。</span><span class="sxs-lookup"><span data-stu-id="e3c13-205">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="e3c13-206">這些值會設定為運算式右邊定義的值。</span><span class="sxs-lookup"><span data-stu-id="e3c13-206">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="e3c13-207">任何其他語言結構（例如[update 和重新指派語句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)）也適用于使用者自訂類型中的名稱專案。</span><span class="sxs-lookup"><span data-stu-id="e3c13-207">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), that are available for array items exist for named-items in user-defined types as well.</span></span>

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

<span data-ttu-id="e3c13-208">使用者定義類型可在任何其他類型可能使用的地方使用。</span><span class="sxs-lookup"><span data-stu-id="e3c13-208">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="e3c13-209">特別是，您可以定義使用者定義型別的陣列，並將使用者定義型別納入為元組型別的元素。</span><span class="sxs-lookup"><span data-stu-id="e3c13-209">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="e3c13-210">請注意，不可能建立遞迴類型結構。</span><span class="sxs-lookup"><span data-stu-id="e3c13-210">Note is not possible to create recursive type structures.</span></span>
<span data-ttu-id="e3c13-211">也就是說，定義使用者自訂類型的類型可能不是包含使用者定義類型之元素的元組類型。</span><span class="sxs-lookup"><span data-stu-id="e3c13-211">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="e3c13-212">一般而言，使用者定義型別可能不會有彼此的迴圈相依性，因此下列型別定義將不合法：</span><span class="sxs-lookup"><span data-stu-id="e3c13-212">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a><span data-ttu-id="e3c13-213">Operation 和 Function 類型</span><span class="sxs-lookup"><span data-stu-id="e3c13-213">Operation and Function Types</span></span>

<span data-ttu-id="e3c13-214">任何可呼叫的基本類型都會寫入為 `('Tinput => 'Tresult)` 或 `('Tinput -> 'Tresult)` ，其中 `'Tinput` 和 `'Tresult` 都是類型。</span><span class="sxs-lookup"><span data-stu-id="e3c13-214">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="e3c13-215">這些稱為可呼叫*的簽*章。</span><span class="sxs-lookup"><span data-stu-id="e3c13-215">These are called the *signature* of the callable.</span></span>

<span data-ttu-id="e3c13-216">所有 Q # callables 都會被視為採用單一值做為輸入，並傳回單一值做為輸出。</span><span class="sxs-lookup"><span data-stu-id="e3c13-216">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="e3c13-217">輸入和輸出值皆可為元組。</span><span class="sxs-lookup"><span data-stu-id="e3c13-217">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="e3c13-218">沒有傳回結果的 Callables `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-218">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="e3c13-219">沒有輸入的 Callables 會採用空的元組做為輸入。</span><span class="sxs-lookup"><span data-stu-id="e3c13-219">Callables that have no input take the empty tuple as input.</span></span>

> [!NOTE]
> <span data-ttu-id="e3c13-220">第一個使用的形式 `=>` 會用於作業，第二個表單則用於函式 `->` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-220">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
> <span data-ttu-id="e3c13-221">例如， `((Qubit, Pauli) => Result)` 代表可能的單一 qubit 測量作業的簽章。</span><span class="sxs-lookup"><span data-stu-id="e3c13-221">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>
<span data-ttu-id="e3c13-222">函*式類型是*由其簽章完整指定。</span><span class="sxs-lookup"><span data-stu-id="e3c13-222">*Function* types are completely specified by their signature.</span></span>
<span data-ttu-id="e3c13-223">例如，計算角度之正弦函數的函式會有類型 `(Double -> Double)` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-223">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="e3c13-224">*作業*---但不是函式---會有特定的其他特性，會表示為操作類型的一部分。</span><span class="sxs-lookup"><span data-stu-id="e3c13-224">*Operations*---but not functions---have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="e3c13-225">這類特性包含作業所支援之*函子*的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e3c13-225">Such characteristics include information about what *functors* the operation supports.</span></span>
<span data-ttu-id="e3c13-226">例如，如果作業的執行可以根據其他 qubits 的狀態進行條件運算，它應該支援 `Controlled` 仿函數; 如果作業具有反向運算，則應該支援 `Adjoint` 仿函數。</span><span class="sxs-lookup"><span data-stu-id="e3c13-226">For example, if execution of the operation can be conditioned on the state of other qubits, it should support the `Controlled` functor; if the operation has an inverse, it should support the `Adjoint` functor.</span></span> <span data-ttu-id="e3c13-227">在[Q # 的作業和](xref:microsoft.quantum.guide.operationsfunctions)函式中會詳細討論函子和作業，但這裡我們只會討論這會如何改變作業簽章。</span><span class="sxs-lookup"><span data-stu-id="e3c13-227">Functors and operations are discussed in detail at [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions), but here we simply discuss how this alters the operation signature.</span></span>

<span data-ttu-id="e3c13-228">若要在作業 `Controlled` 類型中要求支援和/或 `Adjoint` 仿函數，我們需要新增指出對應特性的注釋。</span><span class="sxs-lookup"><span data-stu-id="e3c13-228">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="e3c13-229">注釋 `is Ctl` （例如 `(Qubit => Unit is Ctl)` ）表示作業可控制---也就是，它是在另一個 qubit 或 qubits 的狀態下執行。</span><span class="sxs-lookup"><span data-stu-id="e3c13-229">An annotation `is Ctl` (e.g. `(Qubit => Unit is Ctl)`) indicates that the operation is controllable---that is, it's execution conditioned on the state of another qubit or qubits.</span></span> <span data-ttu-id="e3c13-230">同樣地， `is Adj` 表示作業具有 adjoint; 或者只是「反轉」，這樣會連續套用作業，而其 adjoint 狀態會使狀態保持不變。</span><span class="sxs-lookup"><span data-stu-id="e3c13-230">Similarly, `is Adj` indicates that the operation has an adjoint; or simply, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="e3c13-231">如果我們想要要求該類型的作業同時支援 `Adjoint` 和 `Controlled` 仿函數，我們可以將此表示為 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-231">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="e3c13-232">例如，內建的 Pauli 作業 <xref:microsoft.quantum.intrinsic.x> 具有類型 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-232">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="e3c13-233">不支援任何函子的作業類型是由其輸入和輸出類型單獨指定，沒有額外的注釋。</span><span class="sxs-lookup"><span data-stu-id="e3c13-233">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="e3c13-234">型別參數化函數和作業</span><span class="sxs-lookup"><span data-stu-id="e3c13-234">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="e3c13-235">可呼叫類型可能包含型別參數。</span><span class="sxs-lookup"><span data-stu-id="e3c13-235">Callable types may contain type parameters.</span></span>
<span data-ttu-id="e3c13-236">型別參數是以單一引號前面加上的符號來表示。例如， `'A` 是合法的型別參數。</span><span class="sxs-lookup"><span data-stu-id="e3c13-236">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="e3c13-237">如需定義型別參數化 callables 的詳細資料，請[至 Q # 頁面中的作業和函數](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)。</span><span class="sxs-lookup"><span data-stu-id="e3c13-237">Details on defining type-parameterized callables are provided on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) page.</span></span>

<span data-ttu-id="e3c13-238">類型參數在單一簽章中可能會出現一次以上。</span><span class="sxs-lookup"><span data-stu-id="e3c13-238">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="e3c13-239">例如，將另一個函式套用至陣列之每個專案的函式，並傳回所收集的結果會有簽章 `(('A[], 'A->'A) -> 'A[])` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-239">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="e3c13-240">同樣地，傳回兩個作業組合的函式可能會有簽章 `((('A=>'B), ('B=>'C)) -> ('A=>'C))` 。</span><span class="sxs-lookup"><span data-stu-id="e3c13-240">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="e3c13-241">叫用型別參數化可呼叫時，所有具有相同型別參數的引數都必須屬於相同的型別。</span><span class="sxs-lookup"><span data-stu-id="e3c13-241">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="e3c13-242">問 # 並未提供機制來限制可能會替代類型參數的可能類型。</span><span class="sxs-lookup"><span data-stu-id="e3c13-242">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

## <a name="whats-next"></a><span data-ttu-id="e3c13-243">下一步</span><span class="sxs-lookup"><span data-stu-id="e3c13-243">What's Next?</span></span>
<span data-ttu-id="e3c13-244">既然您已瞭解組成 Q # 語言的所有類型，您可以前往[q # 中的類型運算式](xref:microsoft.quantum.guide.expressions)，以瞭解如何建立和操作這些各種類型的運算式。</span><span class="sxs-lookup"><span data-stu-id="e3c13-244">Now that you've seen all the types which comprise the Q# language, you can head to [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to see how to create and manipulate expressions of these various types.</span></span>


