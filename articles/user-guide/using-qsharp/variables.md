---
title: Q 中的變數#
description: 填滿描述
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 407b4ff3570816eb7bdc323a5c5b77dac2d951af
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430895"
---
# <a name="variables-in-q"></a><span data-ttu-id="86478-103">Q 中的變數#</span><span class="sxs-lookup"><span data-stu-id="86478-103">Variables in Q#</span></span>

<span data-ttu-id="86478-104">Q # 區分可變和不可變的符號，或「變數」（已系結/指派給運算式）。</span><span class="sxs-lookup"><span data-stu-id="86478-104">Q# distinguishes between mutable and immutable symbols, or "variables", which are bound/assigned to expressions.</span></span>
<span data-ttu-id="86478-105">一般來說，我們鼓勵使用不可變的符號，因為它可讓編譯器執行更多的優化。</span><span class="sxs-lookup"><span data-stu-id="86478-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="86478-106">系結的左邊是由符號元組和運算式的右手邊所組成。</span><span class="sxs-lookup"><span data-stu-id="86478-106">The left-hand-side of a binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="86478-107">不可變的變數</span><span class="sxs-lookup"><span data-stu-id="86478-107">Immutable Variables</span></span>

<span data-ttu-id="86478-108">您可以使用關鍵字，將 Q # 中任何類型的值指派給變數，以便在作業或函式內重複使用 `let` 。</span><span class="sxs-lookup"><span data-stu-id="86478-108">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>

<span data-ttu-id="86478-109">不可變的系結包含關鍵字 `let` ，後面接著符號或符號元組、等號 `=` 、用來系結符號的運算式，以及終止的分號。</span><span class="sxs-lookup"><span data-stu-id="86478-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="86478-110">例如：</span><span class="sxs-lookup"><span data-stu-id="86478-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="86478-111">這會將特定的 Pauli 運算子陣列指派給變數名稱（或「符號」） `measurementOperator` 。</span><span class="sxs-lookup"><span data-stu-id="86478-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="86478-112">我們不需要明確指定新變數的類型，因為語句右邊的運算式 `let` 是明確的，而且該類型是由編譯器推斷。</span><span class="sxs-lookup"><span data-stu-id="86478-112">We did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="86478-113">使用定義的變數 `let` 是*不可變*的，這表示一旦定義後，就無法再以任何方式變更。</span><span class="sxs-lookup"><span data-stu-id="86478-113">Variables defined using `let` are *immutable*, meaning that once it has been defined, it can no longer be changed in any way.</span></span>
<span data-ttu-id="86478-114">這可提供數個有用的優化，包括優化要重新排序之變數的傳統邏輯，以套用作業的 `Adjoint` 變體。</span><span class="sxs-lookup"><span data-stu-id="86478-114">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="86478-115">可變變數</span><span class="sxs-lookup"><span data-stu-id="86478-115">Mutable Variables</span></span>

<span data-ttu-id="86478-116">做為使用建立變數的替代方法 `let` ， `mutable` 關鍵字會建立一開始使用關鍵字建立之後，*可以*重新系結的可變變數 `set` 。</span><span class="sxs-lookup"><span data-stu-id="86478-116">As an alternative to creating a variable with `let`, the `mutable` keyword will create a mutable variable that *can* be re-bound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="86478-117">宣告和系結為語句一部分的符號， `mutable` 可能會在稍後的程式碼中重新系結至不同的值。</span><span class="sxs-lookup"><span data-stu-id="86478-117">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> <span data-ttu-id="86478-118">如果稍後在程式碼中重新系結符號，它的類型不會變更，且新系結的值必須與該類型相容。</span><span class="sxs-lookup"><span data-stu-id="86478-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="86478-119">可變動符號的重新系結</span><span class="sxs-lookup"><span data-stu-id="86478-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="86478-120">可以使用語句重新系結可變變數 `set` 。</span><span class="sxs-lookup"><span data-stu-id="86478-120">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="86478-121">這類重新系結包含關鍵字 `set` ，後面接著符號或符號元組、等號、將符號重新系結 `=` 至的運算式，以及終止的分號。</span><span class="sxs-lookup"><span data-stu-id="86478-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="86478-122">在這裡，我們提供一些可能的重新系結語句技術範例</span><span class="sxs-lookup"><span data-stu-id="86478-122">Here, we provide some possible examples of rebinding statement techniques</span></span>

### <a name="apply-and-reassign-statements"></a><span data-ttu-id="86478-123">Apply-重新指派語句</span><span class="sxs-lookup"><span data-stu-id="86478-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="86478-124">`set`如果右側是由二元運算子的應用程式所組成，而結果是要重新系結至運算子的左引數，則我們稱之為*apply 和-重新指派*語句的特定種類語句可提供便利的串連方式。</span><span class="sxs-lookup"><span data-stu-id="86478-124">A particular kind of `set`-statement we refer to as an *apply-and-reassign* statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="86478-125">例如，</span><span class="sxs-lookup"><span data-stu-id="86478-125">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="86478-126">`counter`在迴圈的每個反復專案中遞增計數器的值 `for` 。</span><span class="sxs-lookup"><span data-stu-id="86478-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="86478-127">上述程式碼相當於</span><span class="sxs-lookup"><span data-stu-id="86478-127">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="86478-128">所有二元運算子都有類似的語句，其中左邊的型別符合運算式型別。</span><span class="sxs-lookup"><span data-stu-id="86478-128">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="86478-129">這提供了一個簡單的方式來累積值的範例。</span><span class="sxs-lookup"><span data-stu-id="86478-129">This provides for example a convenient way to accumulate values.</span></span>

<span data-ttu-id="86478-130">例如，假設 `qubits` 是 qubits 的 regsiter：</span><span class="sxs-lookup"><span data-stu-id="86478-130">For example, supposing `qubits` is a regsiter of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a><span data-ttu-id="86478-131">Update-重新指派語句</span><span class="sxs-lookup"><span data-stu-id="86478-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="86478-132">右手邊的[複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)會有類似的串連。</span><span class="sxs-lookup"><span data-stu-id="86478-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand-side.</span></span>
<span data-ttu-id="86478-133">同樣地，使用者定義型別中的*命名專案*以及*陣列專案*的*更新和重新指派*語句也會存在。</span><span class="sxs-lookup"><span data-stu-id="86478-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

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

<span data-ttu-id="86478-134">在陣列的案例中， [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 我們的標準程式庫會針對許多常見的陣列初始化和操作需求提供必要的工具，因此可協助避免必須先更新陣列專案。</span><span class="sxs-lookup"><span data-stu-id="86478-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in our standard libraries provides the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="86478-135">Update-重新指派語句會在需要時提供替代方法：</span><span class="sxs-lookup"><span data-stu-id="86478-135">Update-and-reassign statements provide an alternative if needed:</span></span>

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

<span data-ttu-id="86478-136">例如，針對中提供的陣列使用程式庫工具， [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 我們可以輕鬆地定義函式，以傳回 Paulis 的陣列，其中 Pauli at 索引會 `i` 採用指定的值，而所有其他專案都是身分識別。</span><span class="sxs-lookup"><span data-stu-id="86478-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can, for example, easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity.</span></span>

<span data-ttu-id="86478-137">以下是這類函式的兩個定義，第二個則利用我們的處置工具。</span><span class="sxs-lookup"><span data-stu-id="86478-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

<span data-ttu-id="86478-138">我們不會逐一查看陣列中的每個索引，並有條件地將它設定為 `PauliI` 或，因此， `Pauli` 我們可以改為使用 `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 來建立 `PauliI` 的陣列，然後只傳回已在索引處變更特定值的複製和更新運算式 `location` ：</span><span class="sxs-lookup"><span data-stu-id="86478-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or `Pauli`, we can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI`'s, and then simply returning a copy-and-update expression in which we've changed the specifc value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="86478-139">元組解構</span><span class="sxs-lookup"><span data-stu-id="86478-139">Tuple Deconstruction</span></span>

<span data-ttu-id="86478-140">除了指派單一變數之外， `let` 和 `mutable` 關鍵字---或事實上任何其他系結結構，例如 `set` （如下所述）---也允許將[元組類型](xref:microsoft.quantum.guide.types#tuple-types)的內容解壓縮。</span><span class="sxs-lookup"><span data-stu-id="86478-140">In addition to assigning a single variable, the `let` and `mutable` keywords---or in fact any other binding construct, such as `set` (described below)---also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="86478-141">這個表單的指派是用來*解構*該元組的元素。</span><span class="sxs-lookup"><span data-stu-id="86478-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="86478-142">如果系結的右手邊是元組，則該元組在指派時可能會解構。</span><span class="sxs-lookup"><span data-stu-id="86478-142">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="86478-143">這類解構可能牽涉到嵌套的元組，只要右側元組的形狀與符號元組的形狀相容，任何完整或部分解構都是有效的。</span><span class="sxs-lookup"><span data-stu-id="86478-143">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="86478-144">例如：</span><span class="sxs-lookup"><span data-stu-id="86478-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="86478-145">系結範圍</span><span class="sxs-lookup"><span data-stu-id="86478-145">Binding Scopes</span></span>

<span data-ttu-id="86478-146">一般而言，符號系結會超出範圍，而且會在其發生的語句區塊結尾處變成無法執行。</span><span class="sxs-lookup"><span data-stu-id="86478-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="86478-147">這項規則有兩個例外狀況：</span><span class="sxs-lookup"><span data-stu-id="86478-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="86478-148">迴圈之迴圈變數的系結 `for` 是在 for 迴圈主體的範圍內，而不是在迴圈結束之後。</span><span class="sxs-lookup"><span data-stu-id="86478-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="86478-149">迴圈的所有三個部分 `repeat` / `until` （主體、測試和修復）都會被視為單一範圍，因此本文中系結的符號會在測試和修復中提供。</span><span class="sxs-lookup"><span data-stu-id="86478-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="86478-150">對於這兩種類型的迴圈，每次通過迴圈都會在其本身的範圍中執行，因此在稍後的階段中，不會提供來自較早階段的系結。</span><span class="sxs-lookup"><span data-stu-id="86478-150">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="86478-151">如需這些迴圈的詳細資訊，請參閱[控制流程](xref:microsoft.quantum.guide.controlflow)。</span><span class="sxs-lookup"><span data-stu-id="86478-151">Details on these loops can be found at [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="86478-152">內部區塊會繼承外部區塊的符號系結。</span><span class="sxs-lookup"><span data-stu-id="86478-152">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="86478-153">符號只能系結每個區塊一次;定義符號的名稱與範圍內的另一個符號（不是「遮蔽」）並不合法。</span><span class="sxs-lookup"><span data-stu-id="86478-153">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="86478-154">下列順序會是合法的：</span><span class="sxs-lookup"><span data-stu-id="86478-154">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="86478-155">及</span><span class="sxs-lookup"><span data-stu-id="86478-155">and</span></span>

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

<span data-ttu-id="86478-156">但這不合法：</span><span class="sxs-lookup"><span data-stu-id="86478-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="86478-157">如下所示：</span><span class="sxs-lookup"><span data-stu-id="86478-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="whats-next"></a><span data-ttu-id="86478-158">下一步</span><span class="sxs-lookup"><span data-stu-id="86478-158">What's Next?</span></span>
<span data-ttu-id="86478-159">瞭解如何在 Q # 中使用[Qubits](xref:microsoft.quantum.guide.qubits) 。</span><span class="sxs-lookup"><span data-stu-id="86478-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>