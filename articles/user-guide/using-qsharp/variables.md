---
title: '中的變數 Q#'
description: '瞭解如何使用中的不同變數 Q#'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 67c71c09e004d77360902360fefc7a7752e4a829
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690943"
---
# <a name="variables-in-no-locq"></a><span data-ttu-id="f661b-103">中的變數 Q#</span><span class="sxs-lookup"><span data-stu-id="f661b-103">Variables in Q#</span></span>

<span data-ttu-id="f661b-104">Q# 區分可變和不可變的符號，或 *變數* （系結/指派給運算式）。</span><span class="sxs-lookup"><span data-stu-id="f661b-104">Q# distinguishes between mutable and immutable symbols, or *variables* , which are bound/assigned to expressions.</span></span>
<span data-ttu-id="f661b-105">一般情況下，建議使用不可變的符號，因為它可讓編譯器執行更多的優化。</span><span class="sxs-lookup"><span data-stu-id="f661b-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="f661b-106">系結的左邊是由符號元組和運算式的右手邊所組成。</span><span class="sxs-lookup"><span data-stu-id="f661b-106">The left-hand-side of a binding consists of a symbol tuple and the right-hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="f661b-107">不可變變數</span><span class="sxs-lookup"><span data-stu-id="f661b-107">Immutable Variables</span></span>

<span data-ttu-id="f661b-108">您可以使用關鍵字，將任何類型的值指派 Q# 給變數，以便在作業或函式內重複使用 `let` 。</span><span class="sxs-lookup"><span data-stu-id="f661b-108">You can assign a value of any type in Q# to a variable for reuse within an operation or function by using the `let` keyword.</span></span> 

<span data-ttu-id="f661b-109">不可變的系結是由關鍵字組成 `let` ，後面接著符號或符號元組、等號 `=` 、用來系結符號 () s 的運算式，以及終止分號。</span><span class="sxs-lookup"><span data-stu-id="f661b-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="f661b-110">例如：</span><span class="sxs-lookup"><span data-stu-id="f661b-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="f661b-111">這會將 Pauli 運算子的特定陣列指派給變數名稱 (或 "symbol" ) `measurementOperator` 。</span><span class="sxs-lookup"><span data-stu-id="f661b-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="f661b-112">在上述範例中，不需要明確指定新變數的類型，因為語句右邊的運算式 `let` 是明確的，而編譯器會推斷正確的型別。</span><span class="sxs-lookup"><span data-stu-id="f661b-112">In the previous example, there is no need to explicitly specify the type of the new variable, as the expression on the right-hand side of the `let` statement is unambiguous, and the compiler infers the correct type.</span></span> 

<span data-ttu-id="f661b-113">使用定義 `let` 的變數是 *不可變* 的，也就是說，一旦定義之後，就無法再以任何方式變更。</span><span class="sxs-lookup"><span data-stu-id="f661b-113">Variables defined using `let` are *immutable* , meaning that once you define it, you can no longer change it in any way.</span></span>
<span data-ttu-id="f661b-114">這可讓您進行數個有説明的優化作業，包括優化將變數重新排序以套用作業變異的傳統邏輯 `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="f661b-114">This allows for several beneficial optimizations, including optimization of the classical logic that acts on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="f661b-115">可變變數</span><span class="sxs-lookup"><span data-stu-id="f661b-115">Mutable Variables</span></span>

<span data-ttu-id="f661b-116">作為使用建立變數的替代方式 `let` ， `mutable` 關鍵字會建立可變動的變數，該變數一開始是使用關鍵字來建立時 *可以* 重新綁定 `set` 。</span><span class="sxs-lookup"><span data-stu-id="f661b-116">As an alternative to creating a variable with `let`, the `mutable` keyword creates a mutable variable that *can* be rebound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="f661b-117">稍後在程式碼中，您可以將宣告並系結為語句一部分的符號重新系結 `mutable` 至不同的值。</span><span class="sxs-lookup"><span data-stu-id="f661b-117">You can rebind symbols declared and bound as part of a `mutable` statement to a different value later in the code.</span></span> <span data-ttu-id="f661b-118">如果稍後在程式碼中重新系結符號，其類型不會變更，而且新系結的值必須與該類型相容。</span><span class="sxs-lookup"><span data-stu-id="f661b-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value must be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="f661b-119">可變動符號的重新系結</span><span class="sxs-lookup"><span data-stu-id="f661b-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="f661b-120">您可以使用語句來重新系結可變變數 `set` 。</span><span class="sxs-lookup"><span data-stu-id="f661b-120">You can rebind a mutable variable using a `set` statement.</span></span>
<span data-ttu-id="f661b-121">這種重新系結是由關鍵字組成 `set` ，後面接著符號或符號元組、等號 `=` 、用來重新系結符號 () s 的運算式，以及終止分號。</span><span class="sxs-lookup"><span data-stu-id="f661b-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="f661b-122">以下是一些重新系結語句技術的範例。</span><span class="sxs-lookup"><span data-stu-id="f661b-122">The following are some examples of rebinding statement techniques.</span></span>

#### <a name="apply-and-reassign-statements"></a><span data-ttu-id="f661b-123">Apply 和重新指派語句</span><span class="sxs-lookup"><span data-stu-id="f661b-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="f661b-124">`set`如果右手邊是由二元運算子的應用程式所組成，且結果是要重新綁定至運算子的左邊引數，則特定種類的語句（ *apply 和重新指派* 語句）可提供便利的串連方式。</span><span class="sxs-lookup"><span data-stu-id="f661b-124">A particular kind of `set`-statement, the *apply-and-reassign* statement, provides a convenient way of concatenation if the right-hand side consists of the application of a binary operator, and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="f661b-125">例如，套用至物件的</span><span class="sxs-lookup"><span data-stu-id="f661b-125">For example,</span></span>

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="f661b-126">`counter`在迴圈的每個反復專案中遞增計數器的值 `for` 。</span><span class="sxs-lookup"><span data-stu-id="f661b-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="f661b-127">上述程式碼相當於</span><span class="sxs-lookup"><span data-stu-id="f661b-127">The previous code is equivalent to</span></span> 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="f661b-128">所有二元運算子都可以使用類似的語句，其中左邊的型別符合運算式型別。</span><span class="sxs-lookup"><span data-stu-id="f661b-128">Similar statements are available for all binary operators in which the type of the left-hand side matches the expression type.</span></span> <span data-ttu-id="f661b-129">這些語句提供簡單的方式來累積值。</span><span class="sxs-lookup"><span data-stu-id="f661b-129">These statements provide a convenient way to accumulate values.</span></span>

<span data-ttu-id="f661b-130">例如，假設 `qubits` 是量子位的註冊：</span><span class="sxs-lookup"><span data-stu-id="f661b-130">For example, supposing `qubits` is a register of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a><span data-ttu-id="f661b-131">Update 和重新指派語句</span><span class="sxs-lookup"><span data-stu-id="f661b-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="f661b-132">右手邊的 [複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 有類似的串連。</span><span class="sxs-lookup"><span data-stu-id="f661b-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand side.</span></span>
<span data-ttu-id="f661b-133">同樣地，使用者定義型別中的 *命名專案* 以及 *陣列專案* 也會有 *更新和重新指派* 語句。</span><span class="sxs-lookup"><span data-stu-id="f661b-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items* .</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="f661b-134">在陣列的案例中， [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) 標準連結 Q# 庫提供了許多常見的陣列初始化和操作需求所需的工具，因此有助於避免在一開始就必須更新陣列專案。</span><span class="sxs-lookup"><span data-stu-id="f661b-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) in the Q# standard library provides the necessary tools for many common array initialization and manipulation needs, and thus helps avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="f661b-135">更新和重新指派語句會在需要時提供替代：</span><span class="sxs-lookup"><span data-stu-id="f661b-135">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

<span data-ttu-id="f661b-136">例如，您可以使用中所提供之陣列的程式庫工具， [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) 輕鬆地定義函式，以傳回類型的陣列， `Pauli` 其中索引處的 `i` 專案會採用指定的 `Pauli` 值，而所有其他專案則是 () 的身分識別 `PauliI` 。</span><span class="sxs-lookup"><span data-stu-id="f661b-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays), you can, for example, easily define a function that returns an array of `Pauli` types where the element at index `i` takes a given `Pauli` value, and all other entries are the identity (`PauliI`).</span></span>

<span data-ttu-id="f661b-137">以下是這類函式的兩個定義，而第二個則利用我們處置的工具。</span><span class="sxs-lookup"><span data-stu-id="f661b-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

<span data-ttu-id="f661b-138">與其逐一查看陣列中的每個索引，並有條件地將它設定為 `PauliI` 或指定 `pauli` ，您可以改為使用 `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) 來建立 `PauliI` 類型的陣列，然後只傳回已在索引中變更特定值的複製和更新運算式 `location` ：</span><span class="sxs-lookup"><span data-stu-id="f661b-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or the given `pauli`, you can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) to create an array of `PauliI` types, and then simply return a copy-and-update expression in which you've changed the specific value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="f661b-139">元組解構</span><span class="sxs-lookup"><span data-stu-id="f661b-139">Tuple Deconstruction</span></span>

<span data-ttu-id="f661b-140">除了指派單一變數之外，您還可以使用 `let` 和關鍵字（ `mutable` 或任何其他系結結構，例如-） `set` 將 [元組類型](xref:microsoft.quantum.guide.types#tuple-types)的內容解壓縮。</span><span class="sxs-lookup"><span data-stu-id="f661b-140">In addition to assigning a single variable, you can use the `let` and `mutable` keywords - or any other binding construct, such as `set` - to unpack the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="f661b-141">這種形式的指派是用來 *解構* 該元組的元素。</span><span class="sxs-lookup"><span data-stu-id="f661b-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="f661b-142">如果系結的右手邊是元組，則您可以在指派時解構該元組。</span><span class="sxs-lookup"><span data-stu-id="f661b-142">If the right-hand side of the binding is a tuple, then you can deconstruct that tuple upon assignment.</span></span>
<span data-ttu-id="f661b-143">這類解構可以牽涉到嵌套的元組，而只要右邊的元組形狀與符號元組的形狀相容，任何完整或部分解構都有效。</span><span class="sxs-lookup"><span data-stu-id="f661b-143">Such deconstructions can involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right-hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="f661b-144">例如：</span><span class="sxs-lookup"><span data-stu-id="f661b-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="f661b-145">系結範圍</span><span class="sxs-lookup"><span data-stu-id="f661b-145">Binding Scopes</span></span>

<span data-ttu-id="f661b-146">一般而言，符號系結會移出範圍，並在發生的語句區塊結束時變成無法執行。</span><span class="sxs-lookup"><span data-stu-id="f661b-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="f661b-147">這項規則有兩個例外狀況：</span><span class="sxs-lookup"><span data-stu-id="f661b-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="f661b-148">迴圈的迴圈變數系結 `for` 是在 for 迴圈主體的範圍內，而不是在迴圈結束之後。</span><span class="sxs-lookup"><span data-stu-id="f661b-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="f661b-149">迴圈的三個部分 `repeat` / `until` (主體、測試和修復) 作為單一範圍，因此本文中系結的符號可在測試和修復中使用。</span><span class="sxs-lookup"><span data-stu-id="f661b-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) act as a single scope, so symbols that are bound in the body are available in the test and the fixup.</span></span>

<span data-ttu-id="f661b-150">對於這兩種類型的迴圈，每個迴圈都會在它自己的範圍中執行，因此在稍後的階段中，不會提供來自較早傳遞的系結。</span><span class="sxs-lookup"><span data-stu-id="f661b-150">For both types of loops, each pass through the loop runs in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="f661b-151">如需這些迴圈的詳細資訊，請參閱 [控制流程](xref:microsoft.quantum.guide.controlflow)。</span><span class="sxs-lookup"><span data-stu-id="f661b-151">For more information on these loops, see [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="f661b-152">內部區塊繼承外部區塊的符號系結。</span><span class="sxs-lookup"><span data-stu-id="f661b-152">Inner blocks inherit symbol bindings from outer blocks.</span></span>
<span data-ttu-id="f661b-153">您只能針對每個區塊系結一次符號;使用與範圍內的另一個符號相同的名稱來定義符號不合法 (沒有「遮蔽」 ) 。</span><span class="sxs-lookup"><span data-stu-id="f661b-153">You can only bind a symbol once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="f661b-154">以下是合法的序列：</span><span class="sxs-lookup"><span data-stu-id="f661b-154">The following sequences are legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="f661b-155">及</span><span class="sxs-lookup"><span data-stu-id="f661b-155">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

<span data-ttu-id="f661b-156">但這是不合法的：</span><span class="sxs-lookup"><span data-stu-id="f661b-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="f661b-157">如下所示：</span><span class="sxs-lookup"><span data-stu-id="f661b-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="f661b-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f661b-158">Next steps</span></span>

<span data-ttu-id="f661b-159">瞭解如何[Working With Qubits](xref:microsoft.quantum.guide.qubits)在中使用量子位 Q# 。</span><span class="sxs-lookup"><span data-stu-id="f661b-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>