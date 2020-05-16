---
title: Q 中的控制流程#
description: 迴圈、條件等。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: c534e016fcb8b50e66c11ca29c253ba0512acc6e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430946"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="c1478-103">Q 中的控制流程#</span><span class="sxs-lookup"><span data-stu-id="c1478-103">Control Flow in Q#</span></span>

<span data-ttu-id="c1478-104">在作業或函式內，每個語句會依序執行，類似于最常見的命令式傳統語言。</span><span class="sxs-lookup"><span data-stu-id="c1478-104">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="c1478-105">不過，您可以透過三種不同的方式修改這個控制流程：</span><span class="sxs-lookup"><span data-stu-id="c1478-105">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="c1478-106">`if`報表</span><span class="sxs-lookup"><span data-stu-id="c1478-106">`if` statements</span></span>
- <span data-ttu-id="c1478-107">`for`環回</span><span class="sxs-lookup"><span data-stu-id="c1478-107">`for` loops</span></span>
- <span data-ttu-id="c1478-108">`repeat`-`until`環回</span><span class="sxs-lookup"><span data-stu-id="c1478-108">`repeat`-`until` loops</span></span>

<span data-ttu-id="c1478-109">我們會延遲對後者的討論，[如下所示](#repeat-until-success-loop)。</span><span class="sxs-lookup"><span data-stu-id="c1478-109">We defer discussion of the latter to further [below](#repeat-until-success-loop).</span></span>
<span data-ttu-id="c1478-110">`if` `for` 不過，和控制流程結構的處理方式，對大部分的傳統程式設計語言而言都很熟悉。</span><span class="sxs-lookup"><span data-stu-id="c1478-110">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>

<span data-ttu-id="c1478-111">重要的 `for` 是，迴圈和 `if` 語句甚至可以用於自動產生特殊化的作業。</span><span class="sxs-lookup"><span data-stu-id="c1478-111">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="c1478-112">在此情況下，迴圈的 adjoint `for` 會反轉方向，並接受每個反復專案的 adjoint。</span><span class="sxs-lookup"><span data-stu-id="c1478-112">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="c1478-113">這會遵循「鞋與 socks」原則：如果您想要復原並加上「鞋」，您必須先復原鞋，然後再復原「socks」。</span><span class="sxs-lookup"><span data-stu-id="c1478-113">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="c1478-114">如果您還在戴鞋，也能讓您更輕鬆地嘗試並將您的 socks 轉成由於！</span><span class="sxs-lookup"><span data-stu-id="c1478-114">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="if-else-if-else"></a><span data-ttu-id="c1478-115">如果為，則為，否則為。</span><span class="sxs-lookup"><span data-stu-id="c1478-115">If, Else-if, Else</span></span>

<span data-ttu-id="c1478-116">`if`語句支援條件式執行。</span><span class="sxs-lookup"><span data-stu-id="c1478-116">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="c1478-117">其中包含關鍵字 `if` 、左括弧 `(` 、布林運算式、右括弧 `)` 和語句區塊（ _then_區塊）。</span><span class="sxs-lookup"><span data-stu-id="c1478-117">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="c1478-118">這後面可能接著任意數目的 else if 子句，其中每個都包含關鍵字 `elif` 、左括弧 `(` 、布林運算式、右括弧 `)` 和語句區塊（ _else-if_區塊）。</span><span class="sxs-lookup"><span data-stu-id="c1478-118">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="c1478-119">最後，語句可能會選擇性地以 else 子句完成，其中包含關鍵字， `else` 後面接著另一個語句區塊（ _else_區塊）。</span><span class="sxs-lookup"><span data-stu-id="c1478-119">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="c1478-120">`if`條件會進行評估，如果為 true，則會執行 then 區塊。</span><span class="sxs-lookup"><span data-stu-id="c1478-120">The `if` condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="c1478-121">如果條件為 false，則會評估第一個 else if 條件;如果是 true，則為，否則為。</span><span class="sxs-lookup"><span data-stu-id="c1478-121">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="c1478-122">否則，會先測試第二個 [if] 區塊，然後再進行第三個，直到出現具有 true 條件的子句，或沒有其他的 if 子句為止。</span><span class="sxs-lookup"><span data-stu-id="c1478-122">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="c1478-123">如果原始 if 條件和所有 else if 子句評估為 false，則會執行 else 區塊（如果有提供的話）。</span><span class="sxs-lookup"><span data-stu-id="c1478-123">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="c1478-124">請注意，執行的任何區塊會在其本身的範圍中執行。</span><span class="sxs-lookup"><span data-stu-id="c1478-124">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="c1478-125">在、或區塊內所做的系 `if` 結，在 `elif` `else` 其結尾之後不會顯示。</span><span class="sxs-lookup"><span data-stu-id="c1478-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after its end.</span></span>

<span data-ttu-id="c1478-126">例如，</span><span class="sxs-lookup"><span data-stu-id="c1478-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="c1478-127">或</span><span class="sxs-lookup"><span data-stu-id="c1478-127">or</span></span>
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a><span data-ttu-id="c1478-128">For 迴圈</span><span class="sxs-lookup"><span data-stu-id="c1478-128">For Loop</span></span>

<span data-ttu-id="c1478-129">`for`語句支援在整數範圍或陣列上反覆運算。</span><span class="sxs-lookup"><span data-stu-id="c1478-129">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="c1478-130">語句包含關鍵字 `for` 、左括弧 `(` ，後面接著符號或符號元組、關鍵字 `in` 、型別 `Range` 或陣列的運算式、右括弧 `)` 和語句區塊。</span><span class="sxs-lookup"><span data-stu-id="c1478-130">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="c1478-131">語句區塊（迴圈的主體）會重複執行，其中已定義的符號（迴圈變數）會系結至範圍或陣列中的每個值。</span><span class="sxs-lookup"><span data-stu-id="c1478-131">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="c1478-132">請注意，如果範圍運算式評估為空的範圍或陣列，則完全不會執行主體。</span><span class="sxs-lookup"><span data-stu-id="c1478-132">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="c1478-133">在進入迴圈之前，會完整評估運算式，而且在執行迴圈時不會變更。</span><span class="sxs-lookup"><span data-stu-id="c1478-133">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="c1478-134">迴圈變數會系結至迴圈主體的每個進入，並在主體結尾處解除系結。</span><span class="sxs-lookup"><span data-stu-id="c1478-134">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="c1478-135">特別是，在 for 迴圈完成之後，迴圈變數不會系結。</span><span class="sxs-lookup"><span data-stu-id="c1478-135">In particular, the loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="c1478-136">宣告之符號的系結是不可變的，並遵循與其他變數系結相同的規則。</span><span class="sxs-lookup"><span data-stu-id="c1478-136">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="c1478-137">在某些範例中，假設是 qubits 的暫存器 `qubits` （即類型的 `Qubit[]` ），</span><span class="sxs-lookup"><span data-stu-id="c1478-137">For some examples, supposing `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```
<span data-ttu-id="c1478-138">請注意，我們在結尾使用了算術左移的二元運算子， `<<<` 以及可以在[數值運算式](xref:microsoft.quantum.guide.expressions#numeric-expressions)中找到的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c1478-138">Note that at the end we utilized the arithmetic-shift-left binary operator, `<<<`, details of which can be found at [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span></span>


## <a name="repeat-until-success-loop"></a><span data-ttu-id="c1478-139">重複直到-成功迴圈</span><span class="sxs-lookup"><span data-stu-id="c1478-139">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="c1478-140">Q # 語言可讓傳統控制流程相依于測量 qubits 的結果。</span><span class="sxs-lookup"><span data-stu-id="c1478-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="c1478-141">這項功能可讓您執行功能強大的概率小工具，以降低執行 unitaries 的計算成本。</span><span class="sxs-lookup"><span data-stu-id="c1478-141">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="c1478-142">例如，在 Q # 中執行所謂的*重複-成功*（ru）模式是很容易的。</span><span class="sxs-lookup"><span data-stu-id="c1478-142">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="c1478-143">這些 ru 模式是概率的程式，在基本閘道方面具有*預期*的低成本，但真正的成本取決於實際執行，以及各種可能分支的實際交錯。</span><span class="sxs-lookup"><span data-stu-id="c1478-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="c1478-144">為了協助重複執行-成功（ru）模式，Q # 支援結構</span><span class="sxs-lookup"><span data-stu-id="c1478-144">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="c1478-145">其中 `expression` 是評估為類型值的任何有效運算式 `Bool` 。</span><span class="sxs-lookup"><span data-stu-id="c1478-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="c1478-146">執行迴圈主體，然後評估條件。</span><span class="sxs-lookup"><span data-stu-id="c1478-146">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="c1478-147">如果條件為 true，則表示語句已完成;否則，會執行修復，並從迴圈主體開始重新執行語句。</span><span class="sxs-lookup"><span data-stu-id="c1478-147">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>

<span data-ttu-id="c1478-148">重複/結束迴圈的全部三個部分（主體、測試和修復）都會被視為*每個重複*的單一範圍，因此本文中系結的符號會在測試和修復中提供。</span><span class="sxs-lookup"><span data-stu-id="c1478-148">All three portions of a repeat/until loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in the test and in the fixup.</span></span>
<span data-ttu-id="c1478-149">不過，完成修復的執行會結束語句的範圍，因此在本文或修復期間所做的符號系結，無法用於後續的重複。</span><span class="sxs-lookup"><span data-stu-id="c1478-149">However completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="c1478-150">此外，此 `fixup` 語句通常很有用，但不一定是必要的。</span><span class="sxs-lookup"><span data-stu-id="c1478-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="c1478-151">在不需要的情況下，結構</span><span class="sxs-lookup"><span data-stu-id="c1478-151">In cases that it is not needed, the construct</span></span>
```qsharp
repeat {
    // do stuff
}
until (expression);
```
<span data-ttu-id="c1478-152">也是有效的 ru 模式。</span><span class="sxs-lookup"><span data-stu-id="c1478-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="c1478-153">在此頁面底部，我們會提供一些 ru[迴圈的範例](#repeat-until-success-examples)。</span><span class="sxs-lookup"><span data-stu-id="c1478-153">At the bottom of this page we present some [examples of RUS loops](#repeat-until-success-examples).</span></span>

> [!TIP]   
> <span data-ttu-id="c1478-154">避免在函式內使用重複-成功迴圈。</span><span class="sxs-lookup"><span data-stu-id="c1478-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="c1478-155">對應的功能是由函式中的迴圈所提供。</span><span class="sxs-lookup"><span data-stu-id="c1478-155">The corresponding functionality is provided by while loops in functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="c1478-156">While 迴圈</span><span class="sxs-lookup"><span data-stu-id="c1478-156">While Loop</span></span>

<span data-ttu-id="c1478-157">重複直到-成功模式具有非常量子特定的含意。</span><span class="sxs-lookup"><span data-stu-id="c1478-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="c1478-158">它們廣泛用於特定的量子演算法類別中，因此是 Q # 中的專用語言結構。</span><span class="sxs-lookup"><span data-stu-id="c1478-158">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="c1478-159">不過，根據條件中斷的迴圈，在編譯時期，其執行長度會是未知的，需要在量子執行時間中特別小心處理。</span><span class="sxs-lookup"><span data-stu-id="c1478-159">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="c1478-160">另一方面，它們在函式中的用法是 unproblematic，因為這些只包含將在傳統（非量子）硬體上執行的程式碼。</span><span class="sxs-lookup"><span data-stu-id="c1478-160">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="c1478-161">問 # 因此僅支援在函式內使用 while 迴圈。</span><span class="sxs-lookup"><span data-stu-id="c1478-161">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="c1478-162">`while`語句是由關鍵字 `while` 、左括弧 `(` 、條件（亦即布林運算式）、右括弧 `)` 和語句區塊所組成。</span><span class="sxs-lookup"><span data-stu-id="c1478-162">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="c1478-163">只要條件評估為，就會執行語句區塊（迴圈的主體） `true` 。</span><span class="sxs-lookup"><span data-stu-id="c1478-163">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a><span data-ttu-id="c1478-164">Return 陳述式</span><span class="sxs-lookup"><span data-stu-id="c1478-164">Return Statement</span></span>

<span data-ttu-id="c1478-165">Return 語句會結束執行作業或函數，並將值傳回給呼叫者。</span><span class="sxs-lookup"><span data-stu-id="c1478-165">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="c1478-166">其中包含關鍵字 `return` ，後面接著適當類型的運算式和結束分號。</span><span class="sxs-lookup"><span data-stu-id="c1478-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="c1478-167">可呼叫的會傳回空的元組，不 `()` 需要 return 語句。</span><span class="sxs-lookup"><span data-stu-id="c1478-167">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="c1478-168">如果需要提早結束， `return ()` 可以在此案例中使用。</span><span class="sxs-lookup"><span data-stu-id="c1478-168">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="c1478-169">傳回任何其他類型的 Callables 都需要最終傳回語句。</span><span class="sxs-lookup"><span data-stu-id="c1478-169">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="c1478-170">作業中沒有 return 語句的最大數目。</span><span class="sxs-lookup"><span data-stu-id="c1478-170">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="c1478-171">如果語句在區塊內遵循 return 語句，則編譯器可能會發出警告。</span><span class="sxs-lookup"><span data-stu-id="c1478-171">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="c1478-172">例如，</span><span class="sxs-lookup"><span data-stu-id="c1478-172">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="c1478-173">或</span><span class="sxs-lookup"><span data-stu-id="c1478-173">or</span></span>
```qsharp
return ();
```
<span data-ttu-id="c1478-174">或</span><span class="sxs-lookup"><span data-stu-id="c1478-174">or</span></span>
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a><span data-ttu-id="c1478-175">Fail 語句</span><span class="sxs-lookup"><span data-stu-id="c1478-175">Fail Statement</span></span>

<span data-ttu-id="c1478-176">Fail 語句會結束執行作業，並將錯誤值傳回給呼叫者。</span><span class="sxs-lookup"><span data-stu-id="c1478-176">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="c1478-177">其中包含關鍵字 `fail` ，後面接著字串和結尾的分號。</span><span class="sxs-lookup"><span data-stu-id="c1478-177">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="c1478-178">字串會傳回給傳統驅動程式，做為錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="c1478-178">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="c1478-179">作業內的 fail 語句數目沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="c1478-179">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="c1478-180">如果語句在區塊內遵循 fail 語句，則編譯器可能會發出警告。</span><span class="sxs-lookup"><span data-stu-id="c1478-180">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="c1478-181">例如，</span><span class="sxs-lookup"><span data-stu-id="c1478-181">For example,</span></span>
```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="c1478-182">或者，使用[字串插值](xref:microsoft.quantum.guide.expressions#interpolated-strings)，</span><span class="sxs-lookup"><span data-stu-id="c1478-182">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="c1478-183">重複執行-成功範例</span><span class="sxs-lookup"><span data-stu-id="c1478-183">Repeat-Until-Success Examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="c1478-184">適用于無理軸之單一 qubit 旋轉的 ru 模式</span><span class="sxs-lookup"><span data-stu-id="c1478-184">RUS pattern for single qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="c1478-185">在典型的使用案例中，下列 Q # 作業會在 Bloch 球體上，針對 $ （I + 2i Z）/\sqrt $ 的無理軸執行旋轉 {5} 。</span><span class="sxs-lookup"><span data-stu-id="c1478-185">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="c1478-186">這是使用已知的 ru 模式來完成：</span><span class="sxs-lookup"><span data-stu-id="c1478-186">This is accomplished by using a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-mutable-variable-in-scope"></a><span data-ttu-id="c1478-187">範圍內具有可變變數的 ru 迴圈</span><span class="sxs-lookup"><span data-stu-id="c1478-187">RUS loop with mutable variable in scope</span></span>

<span data-ttu-id="c1478-188">這個範例示範如何使用可變動的變數， `finished` 這是在整個重複執行-修復迴圈的範圍內，而且會在迴圈之前初始化，並在修復步驟中更新。</span><span class="sxs-lookup"><span data-stu-id="c1478-188">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a><span data-ttu-id="c1478-189">不含的 ru`fixup`</span><span class="sxs-lookup"><span data-stu-id="c1478-189">RUS without `fixup`</span></span>

<span data-ttu-id="c1478-190">例如，下列程式碼是使用和閘道 $V _3 = （\boldone + 2 i Z）/\sqrt $ 執行重要旋轉閘道的概率電路 {5} `H` `T` 。</span><span class="sxs-lookup"><span data-stu-id="c1478-190">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="c1478-191">迴圈會平均終止于 $ \frac {8} {5} $ 重複。</span><span class="sxs-lookup"><span data-stu-id="c1478-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="c1478-192">如需詳細資訊，請參閱[*重複直到成功：單一 qubit unitaries 的非決定性分解*](https://arxiv.org/abs/1311.1074)（Paetznick 和 Svore，2014）。</span><span class="sxs-lookup"><span data-stu-id="c1478-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="c1478-193">用來準備量子狀態的 ru</span><span class="sxs-lookup"><span data-stu-id="c1478-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="c1478-194">最後，我們會顯示一個 ru 模式範例，以準備量子 state $ \frac {1} {\sqrt {3} } \left （\sqrt {2} \ket {0} + \ket {1} \right） $ （從 $ \ket{+} $ 狀態開始）。</span><span class="sxs-lookup"><span data-stu-id="c1478-194">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="c1478-195">另請參閱[標準程式庫所提供的單元測試範例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)：</span><span class="sxs-lookup"><span data-stu-id="c1478-195">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="c1478-196">這項作業中所顯示的重要程式設計功能，是迴圈中更複雜 `fixup` 的部分，其中牽涉到配量作業，並使用 `AssertProb` 語句來確定在程式中特定點測量量子狀態的機率。</span><span class="sxs-lookup"><span data-stu-id="c1478-196">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="c1478-197">如需和作業的詳細資訊，另請參閱[測試和調試](xref:microsoft.quantum.guide.testingdebugging)程式 [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) 。</span><span class="sxs-lookup"><span data-stu-id="c1478-197">See also [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>


## <a name="whats-next"></a><span data-ttu-id="c1478-198">下一步</span><span class="sxs-lookup"><span data-stu-id="c1478-198">What's Next?</span></span>
<span data-ttu-id="c1478-199">瞭解如何在 Q # 中進行[測試和調試](xref:microsoft.quantum.guide.testingdebugging)。</span><span class="sxs-lookup"><span data-stu-id="c1478-199">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>