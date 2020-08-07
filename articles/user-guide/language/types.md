---
title: 中的類型Q#
description: 瞭解程式設計語言中使用的不同類型 Q# 。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: b034af0b1d3b967b5680403341813407e4412f93
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869591"
---
# <a name="types-in-no-locq"></a><span data-ttu-id="5e502-103">中的類型Q#</span><span class="sxs-lookup"><span data-stu-id="5e502-103">Types in Q#</span></span>

<span data-ttu-id="5e502-104">本文描述型別 Q# 模型和用來指定和使用型別的語法。</span><span class="sxs-lookup"><span data-stu-id="5e502-104">This article describes the Q# type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="5e502-105">如需如何建立和操作這些類型運算式的詳細資訊，請參閱[類型運算式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="5e502-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="5e502-106">我們注意 Q# 到，是*強型*別語言，因此謹慎使用這些型別可協助編譯器在編譯時期提供有關程式的強式保證 Q# 。</span><span class="sxs-lookup"><span data-stu-id="5e502-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="5e502-107">為了盡可能提供最強的保證，中類型之間的轉換 Q# 必須使用表達該轉換的函式呼叫來明確地進行。</span><span class="sxs-lookup"><span data-stu-id="5e502-107">To provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> 
<span data-ttu-id="5e502-108">Q#提供各種功能作為 <xref:microsoft.quantum.convert> 命名空間的一部分。</span><span class="sxs-lookup"><span data-stu-id="5e502-108">Q# provides a variety of such functions as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="5e502-109">另一方面，Upcasts 到相容的型別，就會隱含地發生。</span><span class="sxs-lookup"><span data-stu-id="5e502-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="5e502-110">Q#提供兩種基本類型，直接使用，以及從其他類型產生新類型的各種方式。</span><span class="sxs-lookup"><span data-stu-id="5e502-110">Q# provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="5e502-111">我們會在本文的其餘部分說明每個專案。</span><span class="sxs-lookup"><span data-stu-id="5e502-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="5e502-112">基本類型</span><span class="sxs-lookup"><span data-stu-id="5e502-112">Primitive Types</span></span>

<span data-ttu-id="5e502-113">Q#語言提供下列*基本類型*，您可以直接在程式中使用它們 Q# 。</span><span class="sxs-lookup"><span data-stu-id="5e502-113">The Q# language provides the following *primitive types*, all of which you can use directly in Q# programs.</span></span> <span data-ttu-id="5e502-114">您也可以使用這些基本類型來建立新的類型。</span><span class="sxs-lookup"><span data-stu-id="5e502-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="5e502-115">`Int`類型代表64位帶正負號的整數，例如、、 `2` `107` `-5` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="5e502-116">`BigInt`類型代表任意大小的帶正負號整數，例如、、 `2L` `107L` `-5L` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="5e502-117">此類型是以 .NET 為基礎<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="5e502-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="5e502-118">型.</span><span class="sxs-lookup"><span data-stu-id="5e502-118">type.</span></span>

- <span data-ttu-id="5e502-119">`Double`類型代表雙精確度浮點數，例如、、 `0.0` `-1.3` `4e-7` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="5e502-120">`Bool`類型代表或的布林值 `true` `false` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="5e502-121">`Range`型別代表一連串的整數，以表示 `start..step..stop` 步驟是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="5e502-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="5e502-122">例如， `start .. stop` 對應至 `start..1..stop` ，而 `1..2..7` 代表序列 $ \{ 1、3、5、7 \} $。</span><span class="sxs-lookup"><span data-stu-id="5e502-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="5e502-123">`String`類型是一系列的 Unicode 字元，不是使用者建立後的不透明。</span><span class="sxs-lookup"><span data-stu-id="5e502-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="5e502-124">在發生 `string` 錯誤或診斷事件的情況下，請使用類型向傳統主機報告訊息。</span><span class="sxs-lookup"><span data-stu-id="5e502-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="5e502-125">`Unit`類型只能有一個值 `()` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="5e502-126">使用此類型來表示 Q# 函數或作業不會傳回任何資訊。</span><span class="sxs-lookup"><span data-stu-id="5e502-126">Use this type to indicate that a Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="5e502-127">`Qubit`型別代表量子位或 qubit。</span><span class="sxs-lookup"><span data-stu-id="5e502-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="5e502-128">`Qubit`s 對使用者而言是不透明的。</span><span class="sxs-lookup"><span data-stu-id="5e502-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="5e502-129">除了將它們傳遞至另一個作業以外，唯一可行的作業是測試身分識別 (是否相等) 。</span><span class="sxs-lookup"><span data-stu-id="5e502-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="5e502-130">最後，您會藉 `Qubit` 由呼叫量子處理器 (或量子模擬器) 上的內建指示，在上執行動作。</span><span class="sxs-lookup"><span data-stu-id="5e502-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="5e502-131">`Pauli`類型代表四個單一 Qubit Pauli 運算子的其中一個。</span><span class="sxs-lookup"><span data-stu-id="5e502-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="5e502-132">使用此類型來表示旋轉的基底作業，並指定要測量的可觀察。</span><span class="sxs-lookup"><span data-stu-id="5e502-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="5e502-133">這是具有四個可能值的列舉類型： `PauliI` 、 `PauliX` 、 `PauliY` 和 `PauliZ` ，它們是類型的常數 `Pauli` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="5e502-134">`Result`型別代表測量結果。</span><span class="sxs-lookup"><span data-stu-id="5e502-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="5e502-135">這是具有兩個可能值的列舉類型： `One` 和 `Zero` ，它們是類型的常數 `Result` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="5e502-136">`Zero`表示已測量 + 1 eigenvalue;`One`表示已測量-1 eigenvalue。</span><span class="sxs-lookup"><span data-stu-id="5e502-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="5e502-137">常數、、、、、、 `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` 和 `Zero` 都是中的所有保留符號 Q# 。</span><span class="sxs-lookup"><span data-stu-id="5e502-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="5e502-138">陣列類型</span><span class="sxs-lookup"><span data-stu-id="5e502-138">Array Types</span></span>

* <span data-ttu-id="5e502-139">針對任何有效的 Q# 類型，有一個類型代表該類型的值陣列。</span><span class="sxs-lookup"><span data-stu-id="5e502-139">For any valid Q# type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="5e502-140">例如， `Qubit[]` 和 `(Bool, Pauli)[]` 代表 `Qubit` 值和 `(Bool, Pauli)` 元組值的陣列。</span><span class="sxs-lookup"><span data-stu-id="5e502-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="5e502-141">陣列陣列也是有效的。</span><span class="sxs-lookup"><span data-stu-id="5e502-141">An array of arrays is also valid.</span></span> <span data-ttu-id="5e502-142">在上一個範例中展開，陣列的陣列 `(Bool, Pauli)` 會以表示 `(Bool, Pauli)[][]` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="5e502-143">這個範例 `(Bool, Pauli)[][]` 代表可能是陣列的不規則陣列，而不是矩形二維陣列。</span><span class="sxs-lookup"><span data-stu-id="5e502-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="5e502-144">Q#不支援矩形多維陣列。</span><span class="sxs-lookup"><span data-stu-id="5e502-144">Q# does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="5e502-145">您可以在 Q# 陣列的元素前後使用方括弧，以原始程式碼撰寫陣列值，如中所示 `[PauliI, PauliX, PauliY, PauliZ]` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-145">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="5e502-146">陣列中所有專案的通用基底類型會決定陣列常值的類型。</span><span class="sxs-lookup"><span data-stu-id="5e502-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="5e502-147">因此，使用沒有通用基底類型的元素來建立陣列會引發錯誤。</span><span class="sxs-lookup"><span data-stu-id="5e502-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="5e502-148">如需範例，請參閱[callables 的陣列](xref:microsoft.quantum.guide.expressions#arrays-of-callables)。</span><span class="sxs-lookup"><span data-stu-id="5e502-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="5e502-149">一旦建立之後，就無法變更陣列的元素。</span><span class="sxs-lookup"><span data-stu-id="5e502-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="5e502-150">若要建立已修改的陣列，請使用[update 和-重新指派語句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)或[複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)。</span><span class="sxs-lookup"><span data-stu-id="5e502-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="5e502-151">或者，您可以使用關鍵字，從其大小建立陣列 `new` ：</span><span class="sxs-lookup"><span data-stu-id="5e502-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="5e502-152">使用 core 函 `Length` 式來取得陣列中的專案數目，做為 `Int` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="5e502-153">陣列可以是下標，以取得單一元素或包含陣列元素子集的新陣列。</span><span class="sxs-lookup"><span data-stu-id="5e502-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="5e502-154">陣列的注標是以零為基底，且必須是類型 `Int` 或類型 `Range` ：</span><span class="sxs-lookup"><span data-stu-id="5e502-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="5e502-155">元組類型</span><span class="sxs-lookup"><span data-stu-id="5e502-155">Tuple Types</span></span>

<span data-ttu-id="5e502-156">元組是一種強大的概念 Q# ，用來將值一起收集成單一值，讓您更輕鬆地將其傳遞。</span><span class="sxs-lookup"><span data-stu-id="5e502-156">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="5e502-157">特別是，使用元組標記法時，您可以表示每個作業和可呼叫都只接受一個輸入，而且只會傳回一個輸出。</span><span class="sxs-lookup"><span data-stu-id="5e502-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="5e502-158">假設有零或多個不同的類型 `T0` （ `T1` 、...）， `Tn` 您可以將新的*元組類型*表示為 `(T0, T1, ..., Tn)` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="5e502-159">用來建立新元組類型的類型本身可以是元組，如中所示 `(Int, (Qubit, Qubit))` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="5e502-160">不過，這類的嵌套一定是有限的，因為在任何情況下，元組類型不能包含本身。</span><span class="sxs-lookup"><span data-stu-id="5e502-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="5e502-161">新元組類型的值是由元組中每個類型的值序列所組成的元組。</span><span class="sxs-lookup"><span data-stu-id="5e502-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="5e502-162">例如， `(3, false)` 是其類型為元組類型的元組 `(Int, Bool)` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="5e502-163">您可以建立元組的陣列、陣列的元組、子元組的元組等等。</span><span class="sxs-lookup"><span data-stu-id="5e502-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="5e502-164">從 Q# 0.3， `Unit` 是空元組的*類型*名稱; `()` 會用於空的元組的*值*。</span><span class="sxs-lookup"><span data-stu-id="5e502-164">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="5e502-165">元組實例為不可變。</span><span class="sxs-lookup"><span data-stu-id="5e502-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="5e502-166">Q#不提供一種機制，可在建立元組之後變更其內容。</span><span class="sxs-lookup"><span data-stu-id="5e502-166">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="5e502-167">單一元組等價</span><span class="sxs-lookup"><span data-stu-id="5e502-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="5e502-168">您可以建立單一 (單一元素) 元組 `('T1)` ，例如 `(5)` 或 `([1,2,3])` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="5e502-169">不過，會將 Q# 單一元組視為對等的類型值。</span><span class="sxs-lookup"><span data-stu-id="5e502-169">However, Q# treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="5e502-170">也就是說，和之間沒有任何差異，或介於和之間 `5` `(5)` `5` `(((5)))` ，或介於 `(5, (6))` 和之間 `(5, 6)` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="5e502-171">它就如同寫入一樣有效， `(5)+3` `5+3` 這兩個運算式都會評估為 `8` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="5e502-172">此等價適用于所有用途，包括指派和運算式。</span><span class="sxs-lookup"><span data-stu-id="5e502-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="5e502-173">假設有任何運算式，以括弧括住的相同運算式就是相同類型的運算式。</span><span class="sxs-lookup"><span data-stu-id="5e502-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="5e502-174">例如， `(7)` 是類型的運算式 `Int` ，是類型的運算式， `([1,2,3])` `Int[]` 而 `((1,2))` 是類型的運算式 `(Int, Int)` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="5e502-175">特別是，這表示您可以查看其輸入元組或輸出元組類型具有一個欄位的作業或函式，以接受單一引數或傳回單一值。</span><span class="sxs-lookup"><span data-stu-id="5e502-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="5e502-176">我們將此屬性稱為_單一元組等價_。</span><span class="sxs-lookup"><span data-stu-id="5e502-176">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="5e502-177">使用者定義類型</span><span class="sxs-lookup"><span data-stu-id="5e502-177">User-Defined Types</span></span>

<span data-ttu-id="5e502-178">使用者定義型別宣告包含關鍵字 `newtype` ，後面接著使用者定義型別的名稱、 `=` 、有效的型別規格，以及終止的分號。</span><span class="sxs-lookup"><span data-stu-id="5e502-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="5e502-179">例如：</span><span class="sxs-lookup"><span data-stu-id="5e502-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="5e502-180">每個 Q# 來源檔案可能會宣告任何數目的使用者定義類型。</span><span class="sxs-lookup"><span data-stu-id="5e502-180">Each Q# source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="5e502-181">類型名稱在命名空間中必須是唯一的，而且可能不會與作業和函式名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="5e502-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="5e502-182">使用者定義類型是相異的，即使基底類型相同也是一樣。</span><span class="sxs-lookup"><span data-stu-id="5e502-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="5e502-183">特別是，兩個使用者自訂類型的值之間不會自動轉換，即使基礎類型相同也一樣。</span><span class="sxs-lookup"><span data-stu-id="5e502-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="5e502-184">名稱與匿名專案的比較</span><span class="sxs-lookup"><span data-stu-id="5e502-184">Named vs. anonymous items</span></span>

<span data-ttu-id="5e502-185">檔案 Q# 可能會定義新的命名類型，其中包含任何合法類型的單一值。</span><span class="sxs-lookup"><span data-stu-id="5e502-185">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="5e502-186">針對任何元組類型 `T` ，您可以使用語句來宣告新的使用者定義型別，這是的子類型 `T` `newtype` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="5e502-187">@"microsoft.quantum.math"例如，在命名空間中，複數會定義為使用者定義型別：</span><span class="sxs-lookup"><span data-stu-id="5e502-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="5e502-188">這個語句會建立具有兩個型別之匿名專案的新型別 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="5e502-189">除了匿名專案以外，使用者定義型別也支援*named items* Q# 0.7 版或更高版本的命名專案。</span><span class="sxs-lookup"><span data-stu-id="5e502-189">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="5e502-190">例如，您可以 `Re` 針對代表複數實數部分的雙精度浮點數，將專案命名為，而 `Im` 針對虛部：</span><span class="sxs-lookup"><span data-stu-id="5e502-190">For example, you could name the items to `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="5e502-191">將使用者定義型別中的一個專案命名，並不表示所有專案都必須命名，而且支援任何組合的已命名和未命名專案。</span><span class="sxs-lookup"><span data-stu-id="5e502-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="5e502-192">此外，內部專案也可以命名為。</span><span class="sxs-lookup"><span data-stu-id="5e502-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="5e502-193">例如，如下所定義的類型 `Nested` 具有基礎類型 `(Double, (Int, String))` ，其中只有類型的專案 `Int` 會命名為，而所有其他專案則為匿名。</span><span class="sxs-lookup"><span data-stu-id="5e502-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="5e502-194">命名專案的優點是可以透過*存取運算子*直接存取它們 `::` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="5e502-195">除了為可能複雜的元組類型提供簡短別名之外，定義這類類型的重要優點是，它們可以記錄特定值的意圖。</span><span class="sxs-lookup"><span data-stu-id="5e502-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="5e502-196">回到的範例 `Complex` ，其中一個也可以定義2d 極座標做為使用者定義的型別：</span><span class="sxs-lookup"><span data-stu-id="5e502-196">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="5e502-197">雖然 `Complex` 和兩者都 `Polar` 具有基礎類型，但這 `(Double, Double)` 兩個類型在中完全不相容 Q# ，因此不小心以極座標呼叫複雜數學函式的風險降至最低，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="5e502-197">Even though both `Complex` and `Polar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="5e502-198">使用解除包裝運算子來存取匿名專案</span><span class="sxs-lookup"><span data-stu-id="5e502-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="5e502-199">若要存取匿名專案，請先使用後置運算子來解壓縮已包裝的值 `!` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="5e502-200">使用「解除包裝」運算子， `!` 您可以解壓縮包含在使用者定義型別中的值。</span><span class="sxs-lookup"><span data-stu-id="5e502-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="5e502-201">這類「解除包裝」運算式的類型是使用者定義類型的基礎類型。</span><span class="sxs-lookup"><span data-stu-id="5e502-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="5e502-202">單一解除包裝運算子會解除封裝一層換行。</span><span class="sxs-lookup"><span data-stu-id="5e502-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="5e502-203">使用多個解除包裝運算子來存取已相乘的值。</span><span class="sxs-lookup"><span data-stu-id="5e502-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="5e502-204">例如：</span><span class="sxs-lookup"><span data-stu-id="5e502-204">For example:</span></span>

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

<span data-ttu-id="5e502-205">如需解除包裝運算子的詳細資訊，請參閱[中 Q# 的類型運算式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="5e502-205">For more details on the unwrap operator, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="5e502-206">建立使用者自訂類型的值</span><span class="sxs-lookup"><span data-stu-id="5e502-206">Creating values of user-defined types</span></span>

<span data-ttu-id="5e502-207">藉由呼叫對應的類型來建立使用者自訂類型的值：</span><span class="sxs-lookup"><span data-stu-id="5e502-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="5e502-208">或者，您可以使用[複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)，從現有的值建立新的值。</span><span class="sxs-lookup"><span data-stu-id="5e502-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="5e502-209">就像使用陣列一樣，複製和更新運算式會複製原始運算式的所有專案值，但指定的命名專案除外。</span><span class="sxs-lookup"><span data-stu-id="5e502-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="5e502-210">針對這些例外狀況，這些專案的值是定義于運算式右手邊的值。</span><span class="sxs-lookup"><span data-stu-id="5e502-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="5e502-211">任何其他可用於陣列專案的語言結構（例如， [update 和重新指派語句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)）也會存在於使用者定義類型中的已命名專案。</span><span class="sxs-lookup"><span data-stu-id="5e502-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

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

* <span data-ttu-id="5e502-212">您可以在任何其他類型的任何位置使用使用者定義類型。</span><span class="sxs-lookup"><span data-stu-id="5e502-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="5e502-213">特別是，您可以定義使用者定義型別的陣列，並將使用者定義型別納入為元組型別的元素。</span><span class="sxs-lookup"><span data-stu-id="5e502-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="5e502-214">不可能建立遞迴類型結構。</span><span class="sxs-lookup"><span data-stu-id="5e502-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="5e502-215">也就是說，定義使用者定義型別的型別不能是包含使用者定義型別之元素的元組型別。</span><span class="sxs-lookup"><span data-stu-id="5e502-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="5e502-216">一般而言，使用者定義型別可能不會有彼此的迴圈相依性，因此下列型別定義的集合會無效：</span><span class="sxs-lookup"><span data-stu-id="5e502-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="5e502-217">Operation 和 Function 類型</span><span class="sxs-lookup"><span data-stu-id="5e502-217">Operation and Function Types</span></span>

<span data-ttu-id="5e502-218">假設類型 `'Tinput` 和 `'Tresult` ：</span><span class="sxs-lookup"><span data-stu-id="5e502-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="5e502-219">`('Tinput => 'Tresult)`這是任何*運算*的基本類型，例如 `((Qubit, Pauli) => Result)` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-219">`('Tinput => 'Tresult)` is the basic type for any *operation*, for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="5e502-220">`('Tinput -> 'Tresult)`是任何*函數*的基本類型，例如 `(Int -> Int)` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-220">`('Tinput -> 'Tresult)` is the basic type for any *function*, for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="5e502-221">這些稱為可呼叫*的簽*章。</span><span class="sxs-lookup"><span data-stu-id="5e502-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="5e502-222">所有 Q# callables 都採用單一值做為輸入，並傳回單一值做為輸出。</span><span class="sxs-lookup"><span data-stu-id="5e502-222">All Q# callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="5e502-223">您可以針對輸入和輸出值使用元組。</span><span class="sxs-lookup"><span data-stu-id="5e502-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="5e502-224">沒有結果的 Callables 會傳回 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="5e502-225">沒有輸入的 Callables 會採用空的元組做為輸入。</span><span class="sxs-lookup"><span data-stu-id="5e502-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="5e502-226">函子</span><span class="sxs-lookup"><span data-stu-id="5e502-226">Functors</span></span>

<span data-ttu-id="5e502-227">函*式類型是*由其簽章完整指定。</span><span class="sxs-lookup"><span data-stu-id="5e502-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="5e502-228">例如，計算角度之正弦函數的函式會有類型 `(Double -> Double)` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="5e502-229">*作業*具有特定的其他特性，會表示為運算類型的一部分。</span><span class="sxs-lookup"><span data-stu-id="5e502-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="5e502-230">這類特性包含作業支援哪些*函子*的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5e502-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="5e502-231">例如，如果作業的執行依賴其他 qubits 的狀態，則它應該支援 `Controlled` 仿函數; 如果作業具有反向運算，則應該支援 `Adjoint` 仿函數。</span><span class="sxs-lookup"><span data-stu-id="5e502-231">For example, if the execution of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="5e502-232">本文只討論函子如何改變作業簽章。</span><span class="sxs-lookup"><span data-stu-id="5e502-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="5e502-233">如需函子和作業的詳細資訊，請參閱[中 Q# 的作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="5e502-233">For more details about functors and operations, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="5e502-234">若要 `Controlled` 在作業類型中要求支援和/或 `Adjoint` 仿函數，您必須加入指出對應特性的注釋。</span><span class="sxs-lookup"><span data-stu-id="5e502-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="5e502-235">批註 `is Ctl` (例如， `(Qubit => Unit is Ctl)`) 表示作業是可控制的。</span><span class="sxs-lookup"><span data-stu-id="5e502-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="5e502-236">也就是說，它的執行會依賴另一個 qubit 或 qubits 的狀態。</span><span class="sxs-lookup"><span data-stu-id="5e502-236">That is, its execution relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="5e502-237">同樣地，注釋會 `is Adj` 指出作業具有 adjoint，也就是說，它可以「反轉」，以便連續套用作業，然後將其 adjoint 狀態保留不變。</span><span class="sxs-lookup"><span data-stu-id="5e502-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="5e502-238">如果您想要要求該類型的作業同時支援 `Adjoint` 和 `Controlled` 仿函數，您可以將此表示為 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="5e502-239">例如，內建的 Pauli 作業 <xref:microsoft.quantum.intrinsic.x> 具有類型 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-239">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="5e502-240">不支援任何函子的作業類型是由其輸入和輸出類型單獨指定，沒有額外的注釋。</span><span class="sxs-lookup"><span data-stu-id="5e502-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="5e502-241">型別參數化函數和作業</span><span class="sxs-lookup"><span data-stu-id="5e502-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="5e502-242">可呼叫類型可能包含*型別參數*。</span><span class="sxs-lookup"><span data-stu-id="5e502-242">Callable types may contain *type parameters*.</span></span>
<span data-ttu-id="5e502-243">使用前面加上單引號的符號來表示型別參數;例如， `'A` 是合法的型別參數。</span><span class="sxs-lookup"><span data-stu-id="5e502-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="5e502-244">如需如何定義型別參數化 callables 的詳細資訊和詳細資料，請參閱[中 Q# 的作業和函數](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)。</span><span class="sxs-lookup"><span data-stu-id="5e502-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="5e502-245">類型參數在單一簽章中可能會出現一次以上。</span><span class="sxs-lookup"><span data-stu-id="5e502-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="5e502-246">例如，函數會將另一個函式套用至陣列的每個元素，並傳回所收集的結果具有簽章 `(('A[], 'A->'A) -> 'A[])` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="5e502-247">同樣地，傳回兩個作業組合的函式具有簽章 `((('A=>'B), ('B=>'C)) -> ('A=>'C))` 。</span><span class="sxs-lookup"><span data-stu-id="5e502-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="5e502-248">當您叫用型別參數化可呼叫時，所有具有相同型別參數的引數都必須屬於相同的型別。</span><span class="sxs-lookup"><span data-stu-id="5e502-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="5e502-249">Q#不會提供機制來限制使用者可能用來取代類型參數的可能類型。</span><span class="sxs-lookup"><span data-stu-id="5e502-249">Q# does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e502-250">後續步驟</span><span class="sxs-lookup"><span data-stu-id="5e502-250">Next steps</span></span>

<span data-ttu-id="5e502-251">既然您已瞭解組成語言的所有類型 Q# ，請參閱[中 Q# 的類型運算式](xref:microsoft.quantum.guide.expressions)，以瞭解如何建立和操作這些各種類型的運算式。</span><span class="sxs-lookup"><span data-stu-id="5e502-251">Now that you've seen all the types which comprise the Q# language, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>
