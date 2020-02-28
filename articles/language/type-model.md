---
title: 'Q # 資料類型'
description: '瞭解問答 # 程式設計語言中使用的不同類型，包括內建類型、陣列、元組、作業、函數和使用者定義類型。'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fc4c0b3fed9277c7f9f3ac421330df03c1b30e4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904650"
---
# <a name="the-type-model"></a><span data-ttu-id="a6a13-103">型別模型</span><span class="sxs-lookup"><span data-stu-id="a6a13-103">The Type Model</span></span>

<span data-ttu-id="a6a13-104">本節會配置 Q # 類型模型，並描述用於指定和使用類型的語法。</span><span class="sxs-lookup"><span data-stu-id="a6a13-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="a6a13-105">我們注意到，Q # 是*強型*別語言，因此小心使用這些型別可協助編譯器在編譯時期提供有關 Q # 程式的強式保證。</span><span class="sxs-lookup"><span data-stu-id="a6a13-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="a6a13-106">為了提供最強的保證，在 Q # 中類型之間的轉換必須使用表達該轉換的函式呼叫來明確地進行。</span><span class="sxs-lookup"><span data-stu-id="a6a13-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="a6a13-107"><xref:microsoft.quantum.convert> 命名空間中提供了各種不同的函數。</span><span class="sxs-lookup"><span data-stu-id="a6a13-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="a6a13-108">另一方面，Upcasts 到相容的型別就會隱含地發生。</span><span class="sxs-lookup"><span data-stu-id="a6a13-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="a6a13-109">Q # 同時提供兩種基本類型，可以直接使用，以及從其他類型產生新類型的各種方式。</span><span class="sxs-lookup"><span data-stu-id="a6a13-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="a6a13-110">我們會在本節的其餘部分說明每個。</span><span class="sxs-lookup"><span data-stu-id="a6a13-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="a6a13-111">基本類型</span><span class="sxs-lookup"><span data-stu-id="a6a13-111">Primitive Types</span></span>

<span data-ttu-id="a6a13-112">Q # 語言提供了數種*基本類型*，可從中建造其他類型：</span><span class="sxs-lookup"><span data-stu-id="a6a13-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="a6a13-113">`Int` 類型代表64位帶正負號的整數，例如： `2`、`107`、`-5`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="a6a13-114">`BigInt` 類型代表任意大小的帶正負號整數，例如 `2L`、`107L`、`-5L`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="a6a13-115">此類型是以 .NET 為基礎 <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="a6a13-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="a6a13-116">型.</span><span class="sxs-lookup"><span data-stu-id="a6a13-116">type.</span></span>
- <span data-ttu-id="a6a13-117">`Double` 類型代表雙精確度浮點數，例如： `0.0`、`-1.3`、`4e-7`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="a6a13-118">`Bool` 類型代表可 `true` 或 `false`的布林值。</span><span class="sxs-lookup"><span data-stu-id="a6a13-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="a6a13-119">`Qubit` 類型代表量子位或 qubit。</span><span class="sxs-lookup"><span data-stu-id="a6a13-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="a6a13-120">對使用者而言，`Qubit`是不透明的;除了將它們傳遞至另一個作業以外，唯一可行的作業是測試身分識別（相等）。</span><span class="sxs-lookup"><span data-stu-id="a6a13-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="a6a13-121">最後，`Qubit`上的動作是藉由呼叫量子處理器上的內建指示來執行（或模擬）。</span><span class="sxs-lookup"><span data-stu-id="a6a13-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="a6a13-122">`Pauli` 類型代表四個單一 qubit Pauli 運算子其中之一。</span><span class="sxs-lookup"><span data-stu-id="a6a13-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="a6a13-123">這個型別是用來表示旋轉的基底作業，並指定要測量的可觀察。</span><span class="sxs-lookup"><span data-stu-id="a6a13-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="a6a13-124">這是具有四個可能值的列舉型別： `PauliI`、`PauliX`、`PauliY`和 `PauliZ`，這些都是 `Pauli`類型的常數。</span><span class="sxs-lookup"><span data-stu-id="a6a13-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="a6a13-125">`Result` 類型代表測量結果。</span><span class="sxs-lookup"><span data-stu-id="a6a13-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="a6a13-126">這是具有兩個可能值的列舉類型： `One` 和 `Zero`，這是 `Result`類型的常數。</span><span class="sxs-lookup"><span data-stu-id="a6a13-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="a6a13-127">`Zero` 表示已測量 + 1 eigenvalue;`One` 表示-1 eigenvalue。</span><span class="sxs-lookup"><span data-stu-id="a6a13-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="a6a13-128">`Range` 類型代表一連串的整數，以 `start..step..stop`表示，其中表示步驟是選項。</span><span class="sxs-lookup"><span data-stu-id="a6a13-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="a6a13-129">這是 `start .. stop` 對應至 `start..1..stop`，例如 `1..2..7` 代表序列 $\{1、3、5、7\}$。</span><span class="sxs-lookup"><span data-stu-id="a6a13-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="a6a13-130">`String` 類型是一系列 Unicode 字元，在使用者建立後不會受到任何不透明的排序。</span><span class="sxs-lookup"><span data-stu-id="a6a13-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="a6a13-131">此類型是用來在發生錯誤或診斷事件時，將訊息報告給傳統主機。</span><span class="sxs-lookup"><span data-stu-id="a6a13-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="a6a13-132">`Unit` 類型是只允許一個值 `()`的類型。</span><span class="sxs-lookup"><span data-stu-id="a6a13-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="a6a13-133">這個類型是用來表示 Q # 函式或作業不會傳回任何資訊。</span><span class="sxs-lookup"><span data-stu-id="a6a13-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="a6a13-134">`true`、`false`、`PauliI`、`PauliX`、`PauliY`、`PauliZ`、`One`和 `Zero` 的常數都是 Q # 中的所有保留符號。</span><span class="sxs-lookup"><span data-stu-id="a6a13-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="a6a13-135">陣列類型</span><span class="sxs-lookup"><span data-stu-id="a6a13-135">Array Types</span></span>

<span data-ttu-id="a6a13-136">假設有任何有效的 Q # 類型 `'T`，則會有一個類型，代表 `'T`類型的值陣列。</span><span class="sxs-lookup"><span data-stu-id="a6a13-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="a6a13-137">此陣列類型會以 `'T[]`表示;例如，`Qubit[]` 或 `Int[][]`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="a6a13-138">例如，整數的集合會以 `Int[]`表示，而 `(Bool, Pauli)` 值陣列的陣列則會以 `(Bool, Pauli)[][]`表示。</span><span class="sxs-lookup"><span data-stu-id="a6a13-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="a6a13-139">在第二個範例中，請注意這代表可能不規則的陣列陣列，而不是矩形二維陣列。</span><span class="sxs-lookup"><span data-stu-id="a6a13-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="a6a13-140">問 # 不提供對矩形多維陣列的支援。</span><span class="sxs-lookup"><span data-stu-id="a6a13-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="a6a13-141">陣列值可以使用方括弧括住陣列的元素（如 `[PauliI, PauliX, PauliY, PauliZ]`），以 Q # 原始程式碼撰寫。</span><span class="sxs-lookup"><span data-stu-id="a6a13-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="a6a13-142">陣列常值的類型取決於陣列中所有專案的通用基底類型。</span><span class="sxs-lookup"><span data-stu-id="a6a13-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="a6a13-143">建立陣列之後，就無法變更陣列的元素。</span><span class="sxs-lookup"><span data-stu-id="a6a13-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="a6a13-144">Update-重新指派語句和（或）複製和更新運算式可以用來建立已修改的陣列。</span><span class="sxs-lookup"><span data-stu-id="a6a13-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="a6a13-145">或者，您可以使用 `new` 關鍵字，從其大小建立陣列：</span><span class="sxs-lookup"><span data-stu-id="a6a13-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="a6a13-146">不論是哪一種情況，一旦結構化陣列之後，就可以使用核心函式 `Length` 來取得做為 `Int`的元素數目。</span><span class="sxs-lookup"><span data-stu-id="a6a13-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="a6a13-147">陣列可以使用方括弧括住，並以具有類型 `Int` 或類型 `Range`的下標來取得單一專案或包含陣列元素子集的新陣列。</span><span class="sxs-lookup"><span data-stu-id="a6a13-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="a6a13-148">陣列的注標是以零為基底：</span><span class="sxs-lookup"><span data-stu-id="a6a13-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="a6a13-149">元組類型</span><span class="sxs-lookup"><span data-stu-id="a6a13-149">Tuple Types</span></span>

<span data-ttu-id="a6a13-150">假設有零或多個不同的類型 `T0`、`T1`、...、`Tn`，我們可以將新的*元組類型*表示為 `(T0, T1, ..., Tn)`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="a6a13-151">用來建立新元組類型的類型本身可以是元組，如 `(Int, (Qubit, Qubit))`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="a6a13-152">不過，這類的嵌套一定是有限的，因為在任何情況下，元組類型不能包含本身。</span><span class="sxs-lookup"><span data-stu-id="a6a13-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="a6a13-153">新元組類型的值是由元組中每個類型的值序列所組成的元組。</span><span class="sxs-lookup"><span data-stu-id="a6a13-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="a6a13-154">例如，`(3, false)` 是一個元組，其型別為 `(Int, Bool)`的元組類型。</span><span class="sxs-lookup"><span data-stu-id="a6a13-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="a6a13-155">您可以建立元組的陣列、陣列的元組、子元組的元組等等。</span><span class="sxs-lookup"><span data-stu-id="a6a13-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="a6a13-156">從 Q # 0.3，`Unit` 是空的元組的*型*別名稱;`()` 用於空的元組*值*。</span><span class="sxs-lookup"><span data-stu-id="a6a13-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="a6a13-157">元組實例為不可變。</span><span class="sxs-lookup"><span data-stu-id="a6a13-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="a6a13-158">問 # 未提供在建立後變更元組內容的機制。</span><span class="sxs-lookup"><span data-stu-id="a6a13-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="a6a13-159">元組是一種功能強大的概念，用於整個 Q #，將值一起收集成單一值，使其更容易傳遞。</span><span class="sxs-lookup"><span data-stu-id="a6a13-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="a6a13-160">特別是，使用元組標記法時，我們可以表示每個作業和可呼叫都只接受一個輸入，而且只會傳回一個輸出。</span><span class="sxs-lookup"><span data-stu-id="a6a13-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="a6a13-161">單一元組等價</span><span class="sxs-lookup"><span data-stu-id="a6a13-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="a6a13-162">您可以建立單一（單一元素）元組，`('T1)`，例如 `(5)` 或 `([1,2,3])`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="a6a13-163">不過，Q # 會將單一元組視為完全等同于已括住類型的值。</span><span class="sxs-lookup"><span data-stu-id="a6a13-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="a6a13-164">也就是說，`5` 和 `(5)`之間，或是 `5` 和 `(((5)))`之間，或介於 `(5, (6))` 和 `(5, 6)`之間沒有差異。</span><span class="sxs-lookup"><span data-stu-id="a6a13-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="a6a13-165">此等價適用于所有用途，包括指派和運算式。</span><span class="sxs-lookup"><span data-stu-id="a6a13-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="a6a13-166">撰寫 `5+3`的 `(5)+3` 是有效的，而且這兩個運算式都會評估為 `8`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="a6a13-167">特別是，這表示輸入元組或輸出元組類型具有一個欄位的作業或函數，可以視為接受單一引數或傳回單一值。</span><span class="sxs-lookup"><span data-stu-id="a6a13-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="a6a13-168">我們將此屬性稱為_單一元組等價_。</span><span class="sxs-lookup"><span data-stu-id="a6a13-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="a6a13-169">使用者定義類型</span><span class="sxs-lookup"><span data-stu-id="a6a13-169">User-Defined Types</span></span>

<span data-ttu-id="a6a13-170">Q # 檔案可能會定義新的命名類型，其中包含任何合法類型的單一值。</span><span class="sxs-lookup"><span data-stu-id="a6a13-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="a6a13-171">對於 `T`的任何元組類型，我們可以宣告新的使用者自訂類型，這是使用 `newtype` 語句 `T` 的子類型。</span><span class="sxs-lookup"><span data-stu-id="a6a13-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="a6a13-172">例如，在 @"microsoft.quantum.math" 命名空間中，複數會定義為使用者定義型別：</span><span class="sxs-lookup"><span data-stu-id="a6a13-172">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="a6a13-173">此語句會建立新的類型，其中包含兩個 `Double`類型的匿名專案。</span><span class="sxs-lookup"><span data-stu-id="a6a13-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="a6a13-174">除了匿名專案以外，使用者定義型別也支援從 Q # 0.7 版或更高版本開始的命名專案。</span><span class="sxs-lookup"><span data-stu-id="a6a13-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="a6a13-175">例如，我們可能會將代表複數實數部分的 double `Re` 命名為專案，並為虛數部分 `Im`：</span><span class="sxs-lookup"><span data-stu-id="a6a13-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="a6a13-176">將使用者定義型別中的一個專案命名，並不表示所有專案都必須命名，而且支援任何組合的已命名和未命名專案。</span><span class="sxs-lookup"><span data-stu-id="a6a13-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="a6a13-177">此外，也可以將內部專案命名為。</span><span class="sxs-lookup"><span data-stu-id="a6a13-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="a6a13-178">如以下所定義的類型 `Nested` 為基礎類型 `(Double, (Int, String))`，其中只有類型 `Int` 的專案會命名為，而所有其他專案則為匿名。</span><span class="sxs-lookup"><span data-stu-id="a6a13-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="a6a13-179">命名專案的優點是可以透過存取運算子 `::`直接存取它們。</span><span class="sxs-lookup"><span data-stu-id="a6a13-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="a6a13-180">若要存取另一方面的匿名專案，必須使用後置運算子 `!`將已包裝的值先解壓縮。</span><span class="sxs-lookup"><span data-stu-id="a6a13-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="a6a13-181">「解除包裝」運算子（`!`）允許將使用者定義型別中包含的值解壓縮。</span><span class="sxs-lookup"><span data-stu-id="a6a13-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="a6a13-182">這類「解除包裝」運算式的類型是使用者定義類型的基礎類型。</span><span class="sxs-lookup"><span data-stu-id="a6a13-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="a6a13-183">解除包裝運算子只會解除封裝一層換行。</span><span class="sxs-lookup"><span data-stu-id="a6a13-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="a6a13-184">可以使用多個解除包裝運算子來存取已相乘的值。</span><span class="sxs-lookup"><span data-stu-id="a6a13-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="a6a13-185">例如：</span><span class="sxs-lookup"><span data-stu-id="a6a13-185">For instance:</span></span>

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

<span data-ttu-id="a6a13-186">如需更多詳細資料，請參閱解除包裝[運算式](xref:microsoft.quantum.language.expressions#unwrap-expressions)和[運算子優先順序](xref:microsoft.quantum.language.expressions#operator-precedence)的一節。</span><span class="sxs-lookup"><span data-stu-id="a6a13-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="a6a13-187">使用者定義類型的值可以藉由呼叫對應的類型構造函式來建立：</span><span class="sxs-lookup"><span data-stu-id="a6a13-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="a6a13-188">或者，您可以使用[複製和更新運算式](xref:microsoft.quantum.language.expressions#copy-and-update-expressions)，從現有的值建立新的值。</span><span class="sxs-lookup"><span data-stu-id="a6a13-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="a6a13-189">如同陣列，這類運算式會複製原始運算式的所有專案值，但指定的命名專案除外。</span><span class="sxs-lookup"><span data-stu-id="a6a13-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="a6a13-190">這些值會設定為運算式右邊定義的值。</span><span class="sxs-lookup"><span data-stu-id="a6a13-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="a6a13-191">任何其他語言結構（例如[update 和重新指派語句](xref:microsoft.quantum.language.statements#update-and-reassign-statement)）也適用于使用者定義類型中的已命名專案。</span><span class="sxs-lookup"><span data-stu-id="a6a13-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="a6a13-192">使用者定義類型可在任何其他類型可能使用的地方使用。</span><span class="sxs-lookup"><span data-stu-id="a6a13-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="a6a13-193">特別是，您可以定義使用者定義型別的陣列，並將使用者定義型別納入為元組型別的元素。</span><span class="sxs-lookup"><span data-stu-id="a6a13-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="a6a13-194">不可能建立遞迴類型結構。</span><span class="sxs-lookup"><span data-stu-id="a6a13-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="a6a13-195">也就是說，定義使用者自訂類型的類型可能不是包含使用者定義類型之元素的元組類型。</span><span class="sxs-lookup"><span data-stu-id="a6a13-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="a6a13-196">一般而言，使用者定義型別可能不會有彼此的迴圈相依性，因此下列型別定義將不合法：</span><span class="sxs-lookup"><span data-stu-id="a6a13-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="a6a13-197">除了為可能複雜的元組類型提供簡短的別名之外，定義這類類型的其中一個重要優點是，它們可以記錄特定值的意圖。</span><span class="sxs-lookup"><span data-stu-id="a6a13-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="a6a13-198">回到 `Complex`的範例，其中一個也可以將2D 極座標定義為使用者定義型別：</span><span class="sxs-lookup"><span data-stu-id="a6a13-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="a6a13-199">雖然 `Complex` 和 `Polar` 都有 `(Double, Double)`的基礎類型，但這兩個類型在 Q # 中完全不相容，因此不小心以極座標呼叫複雜數學函數的風險，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a6a13-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="a6a13-200">如此一來，使用者定義型別與中F#的記錄具有類似的角色，例如。</span><span class="sxs-lookup"><span data-stu-id="a6a13-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="a6a13-201">Operation 和 Function 類型</span><span class="sxs-lookup"><span data-stu-id="a6a13-201">Operation and Function Types</span></span>

<span data-ttu-id="a6a13-202">Q _# 作業_是量子副程式。</span><span class="sxs-lookup"><span data-stu-id="a6a13-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="a6a13-203">也就是說，它是包含量子作業的可呼叫常式。</span><span class="sxs-lookup"><span data-stu-id="a6a13-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="a6a13-204">Q # 函式是在量子演算法內_使用的傳統_副程式。</span><span class="sxs-lookup"><span data-stu-id="a6a13-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="a6a13-205">它可能包含傳統程式碼，但不含量子作業。</span><span class="sxs-lookup"><span data-stu-id="a6a13-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="a6a13-206">具體而言，函式可能不會配置或借用 qubits，也不可能呼叫作業。</span><span class="sxs-lookup"><span data-stu-id="a6a13-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="a6a13-207">不過，您可以傳遞作業或 qubits 進行處理。</span><span class="sxs-lookup"><span data-stu-id="a6a13-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="a6a13-208">函式在使用相同的引數呼叫這些函式時，一定會產生相同的結果。</span><span class="sxs-lookup"><span data-stu-id="a6a13-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="a6a13-209">作業和函式統稱為_callables_。</span><span class="sxs-lookup"><span data-stu-id="a6a13-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="a6a13-210">您可以在下面看到一些[範例](#examples)。</span><span class="sxs-lookup"><span data-stu-id="a6a13-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="a6a13-211">所有 Q # callables 都會被視為採用單一值做為輸入，並傳回單一值做為輸出。</span><span class="sxs-lookup"><span data-stu-id="a6a13-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="a6a13-212">輸入和輸出值皆可為元組。</span><span class="sxs-lookup"><span data-stu-id="a6a13-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="a6a13-213">`Unit`不會傳回結果的 Callables。</span><span class="sxs-lookup"><span data-stu-id="a6a13-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="a6a13-214">沒有輸入的 Callables 會採用空的元組做為輸入。</span><span class="sxs-lookup"><span data-stu-id="a6a13-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="a6a13-215">任何可呼叫的基本類型都會寫入為 `('Tinput => 'Tresult)` 或 `('Tinput -> 'Tresult)`，其中 `'Tinput` 和 `'Tresult` 都是類型。</span><span class="sxs-lookup"><span data-stu-id="a6a13-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="a6a13-216">第一個使用 `=>`的表單用於作業;具有 `->`的第二個表單，適用于函式。</span><span class="sxs-lookup"><span data-stu-id="a6a13-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="a6a13-217">例如，`((Qubit, Pauli) => Result)` 代表可能的單一 qubit 測量作業的簽章。</span><span class="sxs-lookup"><span data-stu-id="a6a13-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="a6a13-218">函式類型是由其簽章完整指定。</span><span class="sxs-lookup"><span data-stu-id="a6a13-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="a6a13-219">例如，計算角度之正弦函數的函式會有類型 `(Double -> Double)`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="a6a13-220">作業（但不是函式）具有特定的其他_特性_，會以運算類型的一部分來表示。</span><span class="sxs-lookup"><span data-stu-id="a6a13-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="a6a13-221">這類特性包含作業所支援之函子的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a6a13-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="a6a13-222">函子是會產生基底作業特製化的元運算;請參閱下方的[函子](#functors)。</span><span class="sxs-lookup"><span data-stu-id="a6a13-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="a6a13-223">作業類型是由其輸入類型、輸出類型和其特性所指定。</span><span class="sxs-lookup"><span data-stu-id="a6a13-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="a6a13-224">若要在作業類型中要求支援 `Controlled` 和/或 `Adjoint` 仿函數，我們需要新增指出對應特性的注釋。</span><span class="sxs-lookup"><span data-stu-id="a6a13-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="a6a13-225">例如，注釋 `is Ctl` 表示作業是可控制的。</span><span class="sxs-lookup"><span data-stu-id="a6a13-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="a6a13-226">如果我們想要要求該類型的作業同時支援 `Adjoint` 和 `Controlled` 仿函數，我們可以將其表示為 `(Qubit => Unit is Adj + Ctl)`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="a6a13-227">`Adj` 使用的作業特性和 `Ctl` 嚴格的說，是兩組預先定義的標籤，其中每個標籤都代表特定的作業特性，例如支援特定的仿函數。</span><span class="sxs-lookup"><span data-stu-id="a6a13-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="a6a13-228">因此，`+` 是用來指出這兩個集合的聯集，而 `*` 用來表示交集，也就是這兩個集合的通用標籤。</span><span class="sxs-lookup"><span data-stu-id="a6a13-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="a6a13-229">例如，Pauli `X` 運算的類型 `(Qubit => Unit is Adj + Ctl)`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="a6a13-230">不支援任何函子的作業類型是由其輸入和輸出類型單獨指定，沒有額外的注釋。</span><span class="sxs-lookup"><span data-stu-id="a6a13-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="a6a13-231">型別參數化函數和作業</span><span class="sxs-lookup"><span data-stu-id="a6a13-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="a6a13-232">可呼叫類型可能包含型別參數。</span><span class="sxs-lookup"><span data-stu-id="a6a13-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="a6a13-233">型別參數是以單一引號前面加上的符號來表示。例如，`'A` 是合法的型別參數。</span><span class="sxs-lookup"><span data-stu-id="a6a13-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="a6a13-234">類型參數在單一簽章中可能會出現一次以上。</span><span class="sxs-lookup"><span data-stu-id="a6a13-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="a6a13-235">例如，將另一個函式套用至陣列之每個專案的函式，並傳回所收集的結果會有簽章 `(('A[], 'A->'A) -> 'A[])`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="a6a13-236">同樣地，傳回兩個作業組合的函式可能會有簽章 `((('A=>'B), ('B=>'C)) -> ('A=>'C))`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="a6a13-237">叫用型別參數化可呼叫時，所有具有相同型別參數的引數都必須屬於相同的型別。</span><span class="sxs-lookup"><span data-stu-id="a6a13-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="a6a13-238">問 # 並未提供機制來限制可能會替代類型參數的可能類型。</span><span class="sxs-lookup"><span data-stu-id="a6a13-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="a6a13-239">類型相容性</span><span class="sxs-lookup"><span data-stu-id="a6a13-239">Type Compatibility</span></span>

<span data-ttu-id="a6a13-240">具有其他函子支援的作業可以在具有較少函子的作業中使用，但預期會有相同的簽章。</span><span class="sxs-lookup"><span data-stu-id="a6a13-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="a6a13-241">例如，`(Qubit => Unit is Adj)` 類型的作業可以在預期類型 `(Qubit => Unit)` 作業的任何位置使用。</span><span class="sxs-lookup"><span data-stu-id="a6a13-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="a6a13-242">Q # 是可呼叫傳回類型的協變數：傳回類型的可呼叫 `'A` 與具有相同輸入類型的可呼叫，以及與 `'A` 相容的結果類型相容。</span><span class="sxs-lookup"><span data-stu-id="a6a13-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="a6a13-243">問 # 是相對於輸入類型的逆變性：接受型別 `'A` 做為輸入的可呼叫，與具有相同結果型別的可呼叫，以及與 `'A`相容的輸入型別相容。</span><span class="sxs-lookup"><span data-stu-id="a6a13-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="a6a13-244">也就是，假設有下列定義：</span><span class="sxs-lookup"><span data-stu-id="a6a13-244">That is, given the following definitions:</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="a6a13-245">下列為 true：</span><span class="sxs-lookup"><span data-stu-id="a6a13-245">the following are true:</span></span>

- <span data-ttu-id="a6a13-246">函數 `ConjugateInvertWith` 可以使用 `Invert` 或 `ApplyUnitary`的 `inner` 引數來叫用。</span><span class="sxs-lookup"><span data-stu-id="a6a13-246">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="a6a13-247">函數 `ConjugateUnitaryWith` 可以使用 `ApplyUnitary`的 `inner` 引數來叫用，但不能用 `Invert`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-247">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="a6a13-248">可能會從 `ConjugateInvertWith`傳回 `(Qubit[] => Unit is Adj + Ctl)` 類型的值。</span><span class="sxs-lookup"><span data-stu-id="a6a13-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6a13-249">問 # 0.3 在使用者定義型別的行為上帶來了顯著的差異。</span><span class="sxs-lookup"><span data-stu-id="a6a13-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="a6a13-250">使用者自訂類型會被視為基礎類型的包裝版本，而不是子類型。</span><span class="sxs-lookup"><span data-stu-id="a6a13-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="a6a13-251">這表示在預期基礎類型的值時，使用者自訂類型的值無法使用。</span><span class="sxs-lookup"><span data-stu-id="a6a13-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="a6a13-252">函子</span><span class="sxs-lookup"><span data-stu-id="a6a13-252">Functors</span></span>

<span data-ttu-id="a6a13-253">問 # 中的仿函數是從另一個作業定義新作業的 factory。</span><span class="sxs-lookup"><span data-stu-id="a6a13-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="a6a13-254">函子在定義新作業的執行時，可以存取基底作業的執行。</span><span class="sxs-lookup"><span data-stu-id="a6a13-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="a6a13-255">因此，函子可以執行比傳統更高層級函數更複雜的函式。</span><span class="sxs-lookup"><span data-stu-id="a6a13-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="a6a13-256">函子在 Q # 類型系統中沒有標記法。</span><span class="sxs-lookup"><span data-stu-id="a6a13-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="a6a13-257">因此目前無法將它們系結至變數，或將它們當做引數傳遞。</span><span class="sxs-lookup"><span data-stu-id="a6a13-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="a6a13-258">仿函數的使用方式是將它套用至作業，並傳回新的作業。</span><span class="sxs-lookup"><span data-stu-id="a6a13-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="a6a13-259">例如，將 `Adjoint` 仿函數套用至 `Y` 作業所產生的作業會寫成 `Adjoint Y`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="a6a13-260">接著就可以叫用新的作業，就像任何其他作業一樣。</span><span class="sxs-lookup"><span data-stu-id="a6a13-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="a6a13-261">因此，`Adjoint Y(q1)` 會將 Adjoint 仿函數套用至 `Y` 作業，以產生新作業，並將該新作業套用至 `q1`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="a6a13-262">同樣地，`Controlled X(controls, target)` 會將受控制的仿函數套用至 `X` 作業，以產生新的作業，並將該新作業套用至 `controls` 和 `target`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="a6a13-263">Q # 中的兩個標準函子是 `Adjoint` 和 `Controlled`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="a6a13-264">Adjoint</span><span class="sxs-lookup"><span data-stu-id="a6a13-264">Adjoint</span></span>

<span data-ttu-id="a6a13-265">在量子運算中，作業的 adjoint 是作業的複雜共軛轉置。</span><span class="sxs-lookup"><span data-stu-id="a6a13-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="a6a13-266">若為執行單一運算子的作業，則 adjoint 是運算的反向。</span><span class="sxs-lookup"><span data-stu-id="a6a13-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="a6a13-267">針對只在一組 qubits 上叫用其他單一作業順序的簡單操作，adjoint 的計算方式是將子作業的 adjoints 套用到反向序列中的相同 qubits 上。</span><span class="sxs-lookup"><span data-stu-id="a6a13-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="a6a13-268">給定作業運算式時，可以使用 `Adjoint` 仿函數來形成新的運算運算式。</span><span class="sxs-lookup"><span data-stu-id="a6a13-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="a6a13-269">例如，`Adjoint QFT` 指定 `QFT` 作業的 adjoint。</span><span class="sxs-lookup"><span data-stu-id="a6a13-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="a6a13-270">新作業的簽章和類型與基底作業相同。</span><span class="sxs-lookup"><span data-stu-id="a6a13-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="a6a13-271">特別是，新作業也允許 `Adjoint`，而且只有在基底作業執行時，才會允許 `Controlled`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="a6a13-272">Adjoint 仿函數是它自己的反向;也就是說，`Adjoint Adjoint Op` 一律與 `Op`相同。</span><span class="sxs-lookup"><span data-stu-id="a6a13-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="a6a13-273">管理</span><span class="sxs-lookup"><span data-stu-id="a6a13-273">Controlled</span></span>

<span data-ttu-id="a6a13-274">作業的受控制版本是新的作業，只有在所有控制項 qubits 都處於指定的狀態時，才會有效地套用基底作業。</span><span class="sxs-lookup"><span data-stu-id="a6a13-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="a6a13-275">如果控制項 qubits 在重迭中，則會將基底作業套用 coherently 至重迭的適當部分。</span><span class="sxs-lookup"><span data-stu-id="a6a13-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="a6a13-276">因此，控制的作業通常用來產生會任何牽連。</span><span class="sxs-lookup"><span data-stu-id="a6a13-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="a6a13-277">在 Q # 中，受控制的版本一律接受控制項 qubits 的陣列，而且指定的狀態一律會讓所有控制項 qubits 都處於計算（`PauliZ`） `One` 狀態，$ \ket{1}$。</span><span class="sxs-lookup"><span data-stu-id="a6a13-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="a6a13-278">藉由將適當的單一作業套用至受控制的作業之前的控制項 qubits，然後在受控制的作業之後套用單一作業的反轉，即可達成根據其他狀態進行控制。</span><span class="sxs-lookup"><span data-stu-id="a6a13-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="a6a13-279">例如，將 `X` 作業套用至受控制作業前後的控制項 qubit，會導致作業控制該 qubit 的 `Zero` 狀態（$ \ket{0}$）;在之前和之後套用 `H` 作業將會控制 `PauliX` `One` 狀態，也就是 Pauli X、$ \ket{-} \mathrel{： =} （\ket{0}-\ket{1}）/\sqrt{2}$ 而不是 `PauliZ` `One` 狀態的 1 eigenvalue。</span><span class="sxs-lookup"><span data-stu-id="a6a13-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="a6a13-280">給定作業運算式時，可以使用 `Controlled` 仿函數來形成新的運算運算式。</span><span class="sxs-lookup"><span data-stu-id="a6a13-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="a6a13-281">新作業的簽章是以原始作業的簽章為基礎。</span><span class="sxs-lookup"><span data-stu-id="a6a13-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="a6a13-282">結果型別相同，但輸入型別是具有 qubit 陣列的兩個元組，其會將控制項 qubit 保存為第一個專案，並將原始運算的引數當做第二個元素。</span><span class="sxs-lookup"><span data-stu-id="a6a13-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="a6a13-283">新的作業支援 `Controlled`，而且只有在原始作業執行時，才支援 `Adjoint`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="a6a13-284">如果原始作業只接受單一引數，則會在這裡播放單一元組等價。</span><span class="sxs-lookup"><span data-stu-id="a6a13-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="a6a13-285">例如，`Controlled X` 是 `X` 作業的受控制版本。</span><span class="sxs-lookup"><span data-stu-id="a6a13-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="a6a13-286">`X` 的類型為 `(Qubit => Unit is Adj + Ctl)`，因此 `Controlled X` 的類型為 `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`;由於單一元組等價，這與 `((Qubit[], Qubit) => Unit is Adj + Ctl)`相同。</span><span class="sxs-lookup"><span data-stu-id="a6a13-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="a6a13-287">如果基底作業接受數個引數，請記得將作業之受控制版本的對應引數括在括弧中，以將其轉換為元組。</span><span class="sxs-lookup"><span data-stu-id="a6a13-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="a6a13-288">例如，`Controlled Rz` 是 `Rz` 作業的受控制版本。</span><span class="sxs-lookup"><span data-stu-id="a6a13-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="a6a13-289">`Rz` 具有類型 `((Double, Qubit) => Unit is Adj + Ctl)`，因此 `Controlled Rz` 的類型 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="a6a13-290">因此，`Controlled Rz(controls, (0.1, target))` 是 `Controlled Rz` 的有效調用（請注意 `0.1, target`周圍的括弧）。</span><span class="sxs-lookup"><span data-stu-id="a6a13-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="a6a13-291">另一個範例是，`CNOT(control, target)` 可以實作為 `Controlled X([control], target)`。</span><span class="sxs-lookup"><span data-stu-id="a6a13-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="a6a13-292">如果目標應該由2個 control qubits （CCNOT）控制，我們可以使用 `Controlled X([control1, control2], target)` 語句。</span><span class="sxs-lookup"><span data-stu-id="a6a13-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="a6a13-293">範例</span><span class="sxs-lookup"><span data-stu-id="a6a13-293">Examples</span></span>

<span data-ttu-id="a6a13-294">此 Q # 作業的範例來自[量測](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement)範例。</span><span class="sxs-lookup"><span data-stu-id="a6a13-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="a6a13-295">在作業中，我們可以在這些 qubits 上配置 qubits 並使用量子作業，例如 `H` 和 `X`：</span><span class="sxs-lookup"><span data-stu-id="a6a13-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

<span data-ttu-id="a6a13-296">此函式的範例來自[PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)範例。</span><span class="sxs-lookup"><span data-stu-id="a6a13-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="a6a13-297">它包含純粹的傳統程式碼。</span><span class="sxs-lookup"><span data-stu-id="a6a13-297">It contains purely classical code.</span></span> <span data-ttu-id="a6a13-298">您可以看到，與上述範例不同的是，不會配置任何 qubits，也不會使用任何量子作業。</span><span class="sxs-lookup"><span data-stu-id="a6a13-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="a6a13-299">也可以將函式傳遞給 qubits 以進行處理，如下列[ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis)範例中的範例所示。</span><span class="sxs-lookup"><span data-stu-id="a6a13-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="a6a13-300">Qubits 會傳遞至函式並用於處理，雖然沒有任何點是 qubit 狀態本身已修改。</span><span class="sxs-lookup"><span data-stu-id="a6a13-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
