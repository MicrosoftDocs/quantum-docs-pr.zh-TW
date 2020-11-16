---
title: '中的類型 Q#'
description: '瞭解程式設計語言中所使用的不同類型 Q# 。'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 349138984387cc564cca18ea09c7bf161524b0b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691620"
---
# <a name="types-in-no-locq"></a><span data-ttu-id="f7ec2-103">中的類型 Q#</span><span class="sxs-lookup"><span data-stu-id="f7ec2-103">Types in Q#</span></span>

<span data-ttu-id="f7ec2-104">本文描述型別 Q# 模型，以及用來指定和使用類型的語法。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-104">This article describes the Q# type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="f7ec2-105">如需有關如何建立和操作這些類型之運算式的詳細資訊，請參閱 [類型運算式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="f7ec2-106">我們注意 Q# 到這是一種 *強型* 別語言，可讓編譯器在編譯時期提供程式的強大保證，以利使用這些類型 Q# 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="f7ec2-107">為了盡可能提供最強的保證，中的型別之間的轉換 Q# 必須使用表達該轉換的函式來明確地呼叫。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-107">To provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> 
<span data-ttu-id="f7ec2-108">Q# 提供多個這類功能做為 <xref:Microsoft.Quantum.Convert> 命名空間的一部分。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-108">Q# provides a variety of such functions as a part of the <xref:Microsoft.Quantum.Convert> namespace.</span></span>
<span data-ttu-id="f7ec2-109">相反地，將至相容的型別會隱含地發生。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="f7ec2-110">Q# 提供兩種基本類型，可直接使用，以及各種不同的方式來產生其他類型的新類型。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-110">Q# provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="f7ec2-111">本文的其餘部分將說明每個專案。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="f7ec2-112">基本類型</span><span class="sxs-lookup"><span data-stu-id="f7ec2-112">Primitive Types</span></span>

<span data-ttu-id="f7ec2-113">此 Q# 語言提供下列基本型 *primitive types* 別，您可以直接在程式中使用這些類型 Q# 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-113">The Q# language provides the following *primitive types* , all of which you can use directly in Q# programs.</span></span> <span data-ttu-id="f7ec2-114">您也可以使用這些基本類型來建立新的類型。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="f7ec2-115">此 `Int` 類型代表64位帶正負號的整數，例如， `2` 、 `107` 、 `-5` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="f7ec2-116">`BigInt`類型代表任意大小的帶正負號整數，例如，、 `2L` `107L` 、 `-5L` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="f7ec2-117">此類型是以 .NET 為基礎 <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="f7ec2-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="f7ec2-118">類型。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-118">type.</span></span>

- <span data-ttu-id="f7ec2-119">`Double`型別代表雙精確度浮點數，例如，、 `0.0` `-1.3` 、 `4e-7` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="f7ec2-120">`Bool`類型代表或的布林值 `true` `false` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="f7ec2-121">此 `Range` 類型代表整數序列（以表示）， `start..step..stop` 其中表示步驟是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="f7ec2-122">例如， `start .. stop` 對應至 `start..1..stop` ，並 `1..2..7` 代表序列 $ \{ 1、3、5、7 \} $。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="f7ec2-123">`String`類型是一系列的 Unicode 字元，使用者一經建立就不透明。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="f7ec2-124">在發生 `string` 錯誤或診斷事件的情況下，使用類型來將訊息報告給傳統主控制項。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="f7ec2-125">此 `Unit` 類型只能有一個值 `()` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="f7ec2-126">您可以使用此類型來表示函式或作業不會傳回 Q# 任何資訊。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-126">Use this type to indicate that a Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="f7ec2-127">`Qubit`類型代表量子位或量子位。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="f7ec2-128">`Qubit`對使用者而言是不透明的。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="f7ec2-129">除了將它們傳遞到另一個作業之外，唯一可行的作業是測試身分識別 (相等) 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="f7ec2-130">最後，您會在 `Qubit` 量子處理器 (或量子模擬器) 上呼叫內建指令，以在上執行動作。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="f7ec2-131">此 `Pauli` 類型代表四個單一量子位 Pauli 運算子的其中一個。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="f7ec2-132">您可以使用此類型來表示旋轉的基底作業，並指定要測量的可觀察。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="f7ec2-133">這是具有四個可能值的列舉類型： `PauliI` 、 `PauliX` 、 `PauliY` 和 `PauliZ` ，這是類型的常數 `Pauli` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="f7ec2-134">此 `Result` 類型代表測量結果。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="f7ec2-135">它是具有兩個可能值的列舉類型： `One` 和 `Zero` ，這是類型的常數 `Result` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="f7ec2-136">`Zero` 表示已測量 + 1 eigenvalue; `One` 表示已測量-1 eigenvalue。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="f7ec2-137">常數、、、、、、 `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` 和 `Zero` 都是中的所有保留符號 Q# 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="f7ec2-138">陣列類型</span><span class="sxs-lookup"><span data-stu-id="f7ec2-138">Array Types</span></span>

* <span data-ttu-id="f7ec2-139">對於任何有效的 Q# 型別，都有一個代表該型別值陣列的型別。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-139">For any valid Q# type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="f7ec2-140">例如， `Qubit[]` 和 `(Bool, Pauli)[]` 表示 `Qubit` 值陣列和 `(Bool, Pauli)` 元組值。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="f7ec2-141">陣列的陣列也有效。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-141">An array of arrays is also valid.</span></span> <span data-ttu-id="f7ec2-142">展開先前的範例，陣列的陣列 `(Bool, Pauli)` 表示 `(Bool, Pauli)[][]` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="f7ec2-143">這個範例 `(Bool, Pauli)[][]` 代表可能不規則的陣列陣列，而不是矩形的二維陣列。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="f7ec2-144">Q# 不支援矩形多維度陣列。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-144">Q# does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="f7ec2-145">陣列值可以 Q# 使用方括弧括住陣列的元素，以原始程式碼撰寫，如中所示 `[PauliI, PauliX, PauliY, PauliZ]` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-145">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="f7ec2-146">陣列中所有專案的通用基底類型會決定陣列常值的類型。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="f7ec2-147">因此，使用沒有通用基底類型的元素來建立陣列時，就會引發錯誤。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="f7ec2-148">如需範例，請參閱 [callables 陣列](xref:microsoft.quantum.guide.expressions#arrays-of-callables)。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="f7ec2-149">一旦建立之後，就無法變更陣列的元素。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="f7ec2-150">若要建立已修改的陣列，請使用 [更新和重新指派語句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) 或 [複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="f7ec2-151">或者，您也可以使用關鍵字來建立陣列的大小 `new` ：</span><span class="sxs-lookup"><span data-stu-id="f7ec2-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="f7ec2-152">您可以使用 core 函 `Length` 式，將陣列中的元素數目取得為 `Int` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="f7ec2-153">陣列可以是下標，以取得單一元素或包含陣列元素子集的新陣列。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="f7ec2-154">陣列的下標以零為基底，而且必須是類型 `Int` 或類型 `Range` ：</span><span class="sxs-lookup"><span data-stu-id="f7ec2-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="f7ec2-155">元組類型</span><span class="sxs-lookup"><span data-stu-id="f7ec2-155">Tuple Types</span></span>

<span data-ttu-id="f7ec2-156">元組是一種功能強大的概念 Q# ，可讓您將值一起收集到單一值，使其更容易傳遞。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-156">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="f7ec2-157">尤其是，使用元組標記法時，您可以表示每個作業和可呼叫只會接受一個輸入，而且只會傳回一個輸出。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="f7ec2-158">如果有零或多個不同的類型 `T0` ， `T1` `Tn` 則為，您可以將新的  *元組類型* 表示為 `(T0, T1, ..., Tn)` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="f7ec2-159">用來建立新元組類型的型別本身可以是元組，如下所示 `(Int, (Qubit, Qubit))` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="f7ec2-160">這類的嵌套一律是有限的，但在任何情況下，元組類型都不能包含自己。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="f7ec2-161">新元組類型的值是元組，由元組中每個類型的值序列所組成。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="f7ec2-162">例如， `(3, false)` 是其類型為元組類型的元組 `(Int, Bool)` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="f7ec2-163">您可以建立元組的陣列、陣列的元組、子元組的元組等等。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="f7ec2-164">從 Q# 0.3， `Unit` 是空元組的 *型* 別名稱， `()` 用於空的元組 *值* 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-164">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="f7ec2-165">元組實例是不可變的。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="f7ec2-166">Q# 未提供在建立元組後變更其內容的機制。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-166">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="f7ec2-167">單一元組等價</span><span class="sxs-lookup"><span data-stu-id="f7ec2-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="f7ec2-168">您可以建立單一 (單一元素) 元組 `('T1)` ，例如 `(5)` 或 `([1,2,3])` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="f7ec2-169">不過，會將 Q# 單一元組視為相當於包含之類型的值。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-169">However, Q# treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="f7ec2-170">也就是說，和之間沒有任何差異，或是在和之間沒有差異 `5` `(5)` `5` `(((5)))` `(5, (6))` `(5, 6)` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="f7ec2-171">它就像寫入一樣有效， `(5)+3` `5+3` 這兩個運算式都會評估為 `8` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="f7ec2-172">這種等價適用于所有用途，包括指派和運算式。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="f7ec2-173">假設有任何運算式，則以括弧括住的相同運算式就是相同類型的運算式。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="f7ec2-174">例如，是類型的 `(7)` 運算式 `Int` ， `([1,2,3])` 是類型的運算式， `Int[]` 而且 `((1,2))` 是型別的運算式 `(Int, Int)` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="f7ec2-175">特別是，這表示您可以查看其輸入元組或輸出元組類型具有單一引數或傳回單一值的一或多個作業或函數。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="f7ec2-176">我們將此屬性稱為 _單一元組等價_ 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-176">We refer to this property as _singleton tuple equivalence_ .</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="f7ec2-177">使用者定義類型</span><span class="sxs-lookup"><span data-stu-id="f7ec2-177">User-Defined Types</span></span>

<span data-ttu-id="f7ec2-178">使用者定義型別宣告由關鍵字組成 `newtype` ，後面接著使用者定義型別的名稱、 `=` 、有效的型別規格，以及結束的分號。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="f7ec2-179">例如：</span><span class="sxs-lookup"><span data-stu-id="f7ec2-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="f7ec2-180">每個 Q# 原始程式檔都可以宣告任意數量的使用者定義類型。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-180">Each Q# source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="f7ec2-181">類型名稱在命名空間中必須是唯一的，而且可能不會與作業和函式名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="f7ec2-182">使用者自訂類型是相異的，即使基底類型相同也是一樣。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="f7ec2-183">尤其是在兩個使用者自訂類型的值之間沒有自動轉換，即使基礎類型相同也是一樣。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="f7ec2-184">命名與匿名專案的比較</span><span class="sxs-lookup"><span data-stu-id="f7ec2-184">Named vs. anonymous items</span></span>

<span data-ttu-id="f7ec2-185">檔案 Q# 可以定義新的命名型別，其中包含任何合法型別的單一值。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-185">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="f7ec2-186">針對任何元組型別 `T` ，您可以使用語句宣告新的使用者定義型別，這個型別是的子型別 `T` `newtype` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="f7ec2-187">@"microsoft.quantum.math"例如，在命名空間中，複數是定義為使用者定義型別：</span><span class="sxs-lookup"><span data-stu-id="f7ec2-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="f7ec2-188">這個語句會建立具有兩個型別匿名專案的新型別 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="f7ec2-189">除了匿名專案之外，使用者定義型別也支援 *named items* Q# 0.7 或更高版本的命名專案。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-189">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="f7ec2-190">例如，您可以將專案命名為 `Real` 代表複數實數部分的雙精度浮點數，並 `Imag` 針對虛數部分：</span><span class="sxs-lookup"><span data-stu-id="f7ec2-190">For example, you could name the items to `Real` for the double representing the real part of a complex number and `Imag` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
<span data-ttu-id="f7ec2-191">在使用者定義型別中命名一個專案並不表示所有專案都必須命名為，並支援任何已命名和未命名專案的組合。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="f7ec2-192">此外，也可以將內部專案命名為。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="f7ec2-193">`Nested`例如，如下列所定義的類型具有基礎類型 `(Double, (Int, String))` ，其中只會命名類型的專案 `Int` ，而所有其他專案都是匿名的。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="f7ec2-194">命名專案的優點是可以直接透過 *存取運算子* 來存取它們 `::` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

<span data-ttu-id="f7ec2-195">除了為可能複雜的元組類型提供簡短的別名，定義這類類型的主要優點是它們可以記錄特定值的意圖。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="f7ec2-196">回到的範例 `Complex` ，一個也可以將極座標表示定義為使用者定義型別：</span><span class="sxs-lookup"><span data-stu-id="f7ec2-196">Returning to the example of `Complex`, one could have also defined a polar coordinate represenation as a user-defined type:</span></span>

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

<span data-ttu-id="f7ec2-197">雖然 `Complex` 和兩者都 `ComplexPolar` 具有基礎類型，但是這 `(Double, Double)` 兩種類型在中完全不相容 Q# ，因此可將不小心呼叫複雜數學函式的風險降至最低，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-197">Even though both `Complex` and `ComplexPolar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="f7ec2-198">使用解除包裝運算子存取匿名專案</span><span class="sxs-lookup"><span data-stu-id="f7ec2-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="f7ec2-199">若要存取匿名專案，請先使用後置運算子來將包裝值解壓縮 `!` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="f7ec2-200">使用「解除包裝」運算子時， `!` 您可以將使用者定義型別中包含的值解壓縮。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="f7ec2-201">這種類型的「解除包裝」運算式是使用者定義型別的基礎型別。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="f7ec2-202">單一解除包裝運算子會解除包裝一層換行。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="f7ec2-203">使用多個解除包裝運算子來存取相乘的值。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="f7ec2-204">例如：</span><span class="sxs-lookup"><span data-stu-id="f7ec2-204">For example:</span></span>

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

<span data-ttu-id="f7ec2-205">如需解除包裝運算子的詳細資訊，請參閱[中 Q# 的型別運算式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-205">For more details on the unwrap operator, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="f7ec2-206">建立使用者自訂類型的值</span><span class="sxs-lookup"><span data-stu-id="f7ec2-206">Creating values of user-defined types</span></span>

<span data-ttu-id="f7ec2-207">藉由呼叫對應的型別函式來建立使用者自訂類型的值：</span><span class="sxs-lookup"><span data-stu-id="f7ec2-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="f7ec2-208">或者，您可以使用 [複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)，從現有的值建立新的值。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="f7ec2-209">如同使用陣列，複製和更新運算式會複製原始運算式的所有專案值，但指定的命名專案除外。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="f7ec2-210">針對這些例外狀況，這些專案的值是在運算式右邊定義的值。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="f7ec2-211">任何其他適用于陣列專案的語言結構，例如 [更新和重新指派語句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)，也存在於使用者定義型別中的命名專案。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

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

* <span data-ttu-id="f7ec2-212">您可以使用任何其他類型之任何地方的使用者自訂類型。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="f7ec2-213">尤其是，您可以定義使用者定義型別的陣列，並將使用者定義型別包含為元組類型的元素。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="f7ec2-214">不可能建立遞迴類型結構。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="f7ec2-215">也就是說，定義使用者定義型別的型別不能是包含使用者定義型別之元素的元組類型。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="f7ec2-216">更常見的情況是，使用者定義型別可能沒有彼此的迴圈相依性，因此下列類型定義集合無效：</span><span class="sxs-lookup"><span data-stu-id="f7ec2-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="f7ec2-217">Operation 和 Function 類型</span><span class="sxs-lookup"><span data-stu-id="f7ec2-217">Operation and Function Types</span></span>

<span data-ttu-id="f7ec2-218">假設類型 `'Tinput` 和 `'Tresult` ：</span><span class="sxs-lookup"><span data-stu-id="f7ec2-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="f7ec2-219">`('Tinput => 'Tresult)` 是任何 *運算* 的基本類型，例如 `((Qubit, Pauli) => Result)` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-219">`('Tinput => 'Tresult)` is the basic type for any *operation* , for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="f7ec2-220">`('Tinput -> 'Tresult)` 是任何 *函數* 的基本類型，例如 `(Int -> Int)` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-220">`('Tinput -> 'Tresult)` is the basic type for any *function* , for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="f7ec2-221">這些稱為可呼叫 *的簽* 章。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="f7ec2-222">所有 Q# callables 都採用單一值作為輸入，並傳回單一值作為輸出。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-222">All Q# callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="f7ec2-223">您可以針對輸入和輸出值使用元組。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="f7ec2-224">沒有結果的 Callables，return `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="f7ec2-225">沒有輸入的 Callables 會將空的元組視為輸入。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="f7ec2-226">函子</span><span class="sxs-lookup"><span data-stu-id="f7ec2-226">Functors</span></span>

<span data-ttu-id="f7ec2-227">函 *式類型是* 由其簽章完全指定。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="f7ec2-228">例如，計算角度正弦的函式會有型別 `(Double -> Double)` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="f7ec2-229">*作業* 具有某些其他特性，表示為作業類型的一部分。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="f7ec2-230">這類特性包含作業所支援之 *函子* 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="f7ec2-231">例如，如果執行作業依賴其他量子位的狀態，則它應該支援 `Controlled` 仿函數; 如果作業具有反向，則應該支援 `Adjoint` 仿函數。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-231">For example, if the running of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="f7ec2-232">本文僅討論函子如何改變作業簽章。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="f7ec2-233">如需函子和作業的詳細資訊，請參閱[中的 Q# 作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-233">For more details about functors and operations, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="f7ec2-234">若要 `Controlled` 在作業類型中要求和/或仿函數的支援 `Adjoint` ，您必須加入指出對應特性的注釋。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="f7ec2-235">批註 `is Ctl` (例如， `(Qubit => Unit is Ctl)`) 表示作業可控制。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="f7ec2-236">也就是說，它的執行依賴另一個量子位或量子位的狀態。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-236">That is, its run relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="f7ec2-237">同樣地，批註也會 `is Adj` 指出作業具有 adjoint，也就是它可以「反轉」，以便連續套用作業，然後將其 adjoint 狀態保持不變。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="f7ec2-238">如果您想要要求該類型的作業同時支援 `Adjoint` 和 `Controlled` 仿函數，您可以將它表示為 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="f7ec2-239">例如，內建的 Pauli 作業 <xref:Microsoft.Quantum.Intrinsic.X> 具有類型 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-239">For example, the built-in Pauli <xref:Microsoft.Quantum.Intrinsic.X> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="f7ec2-240">不支援任何函子的作業類型是由其輸入和輸出類型單獨指定，不含其他注釋。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="f7ec2-241">Type-Parameterized 函數和作業</span><span class="sxs-lookup"><span data-stu-id="f7ec2-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="f7ec2-242">可呼叫的類型可以包含 *型別參數* 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-242">Callable types may contain *type parameters* .</span></span>
<span data-ttu-id="f7ec2-243">使用前面加上單引號的符號來指出型別參數;例如， `'A` 是合法的型別參數。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="f7ec2-244">如需如何定義型別參數化 callables 的詳細資訊和詳細資訊，請參閱[中 Q# 的作業和函數](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="f7ec2-245">類型參數在單一簽章中可能會出現一次以上。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="f7ec2-246">例如，函式會將另一個函式套用至陣列的每個元素，並傳回所收集的結果 `(('A[], 'A->'A) -> 'A[])` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="f7ec2-247">同樣地，傳回兩個作業組合的函式會有簽章 `((('A=>'B), ('B=>'C)) -> ('A=>'C))` 。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="f7ec2-248">當您叫用型別參數化的可呼叫時，具有相同類型參數的所有引數都必須屬於相同類型。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="f7ec2-249">Q# 不會提供一種機制，以限制使用者可能用來取代類型參數的可能類型。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-249">Q# does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f7ec2-250">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f7ec2-250">Next steps</span></span>

<span data-ttu-id="f7ec2-251">現在您已瞭解組成語言的所有 Q# 型別，請參閱[ Q# 中的型別運算式](xref:microsoft.quantum.guide.expressions)，以瞭解如何建立和操作這些各種類型的運算式。</span><span class="sxs-lookup"><span data-stu-id="f7ec2-251">Now that you've seen all the types which comprise the Q# language, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>
