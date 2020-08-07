---
title: 中的控制流程Q#
description: 迴圈、條件等。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: fc619d64bfebfc27d7feac6dafb2dd4cf22825d6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867942"
---
# <a name="control-flow-in-no-locq"></a><span data-ttu-id="d8f8b-103">中的控制流程Q#</span><span class="sxs-lookup"><span data-stu-id="d8f8b-103">Control flow in Q#</span></span>

<span data-ttu-id="d8f8b-104">在作業或函式中，每個語句會依序執行，類似于其他常見的命令式傳統語言。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="d8f8b-105">不過，您可以用三種不同的方式修改控制流程：</span><span class="sxs-lookup"><span data-stu-id="d8f8b-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="d8f8b-106">`if`報表</span><span class="sxs-lookup"><span data-stu-id="d8f8b-106">`if` statements</span></span>
* <span data-ttu-id="d8f8b-107">`for`環回</span><span class="sxs-lookup"><span data-stu-id="d8f8b-107">`for` loops</span></span>
* <span data-ttu-id="d8f8b-108">`repeat-until-success`環回</span><span class="sxs-lookup"><span data-stu-id="d8f8b-108">`repeat-until-success` loops</span></span>

<span data-ttu-id="d8f8b-109">`if`和 `for` 控制流程結構會以熟悉的方式進行大部分的傳統程式設計語言。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-109">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="d8f8b-110">[`Repeat-until-success`](#repeat-until-success-loop)本文稍後會討論迴圈。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-110">[`Repeat-until-success`](#repeat-until-success-loop) loops are discussed later in this article.</span></span>

<span data-ttu-id="d8f8b-111">重要的 `for` 是，迴圈和 `if` 語句可以用於自動產生[特殊化](xref:microsoft.quantum.guide.operationsfunctions)的作業。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-111">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="d8f8b-112">在該案例中，迴圈的 adjoint `for` 會反轉方向，並接受每個反復專案的 adjoint。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-112">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="d8f8b-113">此動作會遵循「鞋與 socks」原則：如果您想要復原並加上「鞋」，您必須先復原鞋，然後再復原「socks」。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-113">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="d8f8b-114">如果為，則為，否則為。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-114">If, Else-if, Else</span></span>

<span data-ttu-id="d8f8b-115">`if`語句支援條件式執行。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-115">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="d8f8b-116">其中包含關鍵字 `if` 、括弧中的布林運算式，以及 (_then_區塊) 的語句區塊。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-116">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="d8f8b-117">或者，任何數目的 else if 子句可以跟著遵循，其中每一個都包含關鍵字 `elif` 、括弧中的布林運算式，以及 (_else-if_區塊) 的語句區塊。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-117">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="d8f8b-118">最後，語句可以選擇性地完成 else 子句，其中包含關鍵字， `else` 後面接著另一個語句區塊 (_else_區塊) 。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-118">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="d8f8b-119">`if`條件會進行評估，如果為*true*，則會執行*then*區塊。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-119">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="d8f8b-120">如果條件為*false*，則會評估第一個 else if 條件;如果為 true，則會執行*else-if*區塊。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-120">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="d8f8b-121">否則，第二個 [if] 區塊會評估，然後是第三個，直到出現具有 true 條件的子句，或沒有其他的 if 子句為止。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-121">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="d8f8b-122">如果原始*if*條件和所有 else if 子句評估為*false*，則會執行*else*區塊（如果有提供的話）。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-122">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="d8f8b-123">請注意，不論是哪一種區塊執行，它都會在自己的範圍內執行。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-123">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="d8f8b-124">`if` `elif` `else` 區塊結束之後，不會顯示在、或區塊內所做的系結。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-124">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="d8f8b-125">例如</span><span class="sxs-lookup"><span data-stu-id="d8f8b-125">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="d8f8b-126">或</span><span class="sxs-lookup"><span data-stu-id="d8f8b-126">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="d8f8b-127">For 迴圈</span><span class="sxs-lookup"><span data-stu-id="d8f8b-127">For loop</span></span>

<span data-ttu-id="d8f8b-128">`for`語句支援在整數範圍或陣列上反覆運算。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-128">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="d8f8b-129">語句包含關鍵字 `for` ，後面接著符號或符號元組、關鍵字 `in` ，以及類型 `Range` 或陣列的運算式、全部在括弧中，以及語句區塊。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-129">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="d8f8b-130">語句區塊 (迴圈的主體，) 重複執行，並以定義的符號 (迴圈變數) 系結至範圍或陣列中的每個值。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-130">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="d8f8b-131">請注意，如果範圍運算式評估為空白範圍或陣列，則不會執行主體。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-131">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="d8f8b-132">在進入迴圈之前，會完整評估運算式，而且在執行迴圈時不會變更。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-132">The expression is fully evaluated before entering the loop, and does not change while the loop is executing.</span></span>

<span data-ttu-id="d8f8b-133">迴圈變數會系結至迴圈主體的每個進入，並在主體結尾處解除系結。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-133">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="d8f8b-134">在 for 迴圈完成之後，迴圈變數不會系結。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-134">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="d8f8b-135">迴圈變數的系結是不可變的，並遵循與其他變數系結相同的規則。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-135">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="d8f8b-136">在這些範例中，是 qubits 的暫存器 `qubits` ，也就是) 類型的 (。 `Qubit[]`</span><span class="sxs-lookup"><span data-stu-id="d8f8b-136">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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

<span data-ttu-id="d8f8b-137">請注意，我們在結尾使用了算術左移的二元運算子 `<<<` 。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-137">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="d8f8b-138">如需詳細資訊，請參閱[數值運算式](xref:microsoft.quantum.guide.expressions#numeric-expressions)。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-138">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="d8f8b-139">重複直到-成功迴圈</span><span class="sxs-lookup"><span data-stu-id="d8f8b-139">Repeat-until-success loop</span></span>

<span data-ttu-id="d8f8b-140">此 Q# 語言可讓傳統控制流程相依于測量 qubits 的結果。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="d8f8b-141">這項功能可讓您執行功能強大的概率小工具，以降低執行 unitaries 的計算成本。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-141">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="d8f8b-142">這種情況的範例是 (ru) 模式的*重複直到成功為止* Q# 。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-142">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="d8f8b-143">這些 ru 模式是概率的程式，在基本閘道方面具有*預期*的低成本;產生的成本取決於實際執行，以及多個可能分支的交錯。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="d8f8b-144">為了協助重複執行-成功 (ru) 模式， Q# 支援結構</span><span class="sxs-lookup"><span data-stu-id="d8f8b-144">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="d8f8b-145">其中 `expression` 是評估為類型值的任何有效運算式 `Bool` 。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="d8f8b-146">迴圈主體會執行，然後評估條件。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-146">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="d8f8b-147">如果條件為 true，則表示語句已完成;否則，會執行修復，而且語句會從迴圈主體開始再次執行。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-147">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="d8f8b-148">Ru 迴圈的全部三個部分 (主體、測試和修復) 會被視為*每個重複*的單一範圍，因此，在本文中系結的符號會同時在測試和修復中提供。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-148">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="d8f8b-149">不過，完成修復的執行會結束語句的範圍，因此在本文或修復期間所做的符號系結，無法用於後續的重複。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-149">However, completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="d8f8b-150">此外，此 `fixup` 語句通常很有用，但不一定是必要的。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="d8f8b-151">在不需要的情況下，結構</span><span class="sxs-lookup"><span data-stu-id="d8f8b-151">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="d8f8b-152">也是有效的 ru 模式。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="d8f8b-153">如需更多範例和詳細資料，請參閱本文中的[重複執行-成功範例](#repeat-until-success-examples)。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-153">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="d8f8b-154">避免在函式內使用重複-成功迴圈。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="d8f8b-155">使用*while*迴圈來提供函式內的對應功能。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-155">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="d8f8b-156">While 迴圈</span><span class="sxs-lookup"><span data-stu-id="d8f8b-156">While loop</span></span>

<span data-ttu-id="d8f8b-157">重複直到-成功模式具有非常量子特定的含意。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="d8f8b-158">它們廣泛用於特定的量子演算法類別中，因此是中的專用語言結構 Q# 。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-158">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="d8f8b-159">不過，根據條件中斷的迴圈，在編譯時期，其執行長度會是未知的，會在量子執行時間中特別小心處理。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-159">However, loops that break based on a condition and whose execution length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="d8f8b-160">不過，它們在函式中的用法是 unproblematic 的，因為這些迴圈只包含在傳統 (非量子) 硬體上執行的程式碼。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-160">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="d8f8b-161">Q#因此，只支援在函式內使用 while 迴圈。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-161">Q#, therefore, supports to use of while loops within functions only.</span></span> <span data-ttu-id="d8f8b-162">`while`語句包含關鍵字 `while` 、括弧中的布林運算式，以及語句區塊。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-162">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="d8f8b-163">語句區塊 (迴圈的主體) 執行，只要條件評估為 `true` 。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-163">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a><span data-ttu-id="d8f8b-164">Return 陳述式</span><span class="sxs-lookup"><span data-stu-id="d8f8b-164">Return Statement</span></span>

<span data-ttu-id="d8f8b-165">Return 語句會結束作業或函數的執行，並將值傳回給呼叫者。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-165">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="d8f8b-166">其中包含關鍵字 `return` ，後面接著適當類型的運算式和結束分號。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="d8f8b-167">例如</span><span class="sxs-lookup"><span data-stu-id="d8f8b-167">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="d8f8b-168">或</span><span class="sxs-lookup"><span data-stu-id="d8f8b-168">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="d8f8b-169">可呼叫的會傳回空的元組，不 `()` 需要 return 語句。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-169">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="d8f8b-170">若要指定從作業或函式提早結束，請使用 `return ();` 。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-170">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="d8f8b-171">傳回任何其他類型的 Callables 都需要最終傳回語句。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-171">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="d8f8b-172">作業中沒有 return 語句的最大數目。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-172">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="d8f8b-173">如果語句在區塊內遵循 return 語句，則編譯器可能會發出警告。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-173">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="d8f8b-174">Fail 語句</span><span class="sxs-lookup"><span data-stu-id="d8f8b-174">Fail statement</span></span>

<span data-ttu-id="d8f8b-175">Fail 語句會結束作業的執行，並將錯誤值傳回給呼叫者。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-175">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="d8f8b-176">其中包含關鍵字 `fail` ，後面接著字串和結尾的分號。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-176">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="d8f8b-177">語句會將字串傳回給傳統驅動程式，做為錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-177">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="d8f8b-178">作業內的 fail 語句數目沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-178">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="d8f8b-179">如果語句在區塊內遵循 fail 語句，則編譯器可能會發出警告。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-179">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="d8f8b-180">例如</span><span class="sxs-lookup"><span data-stu-id="d8f8b-180">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="d8f8b-181">或者，使用[字串插值](xref:microsoft.quantum.guide.expressions#interpolated-strings)，</span><span class="sxs-lookup"><span data-stu-id="d8f8b-181">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="d8f8b-182">重複執行-成功範例</span><span class="sxs-lookup"><span data-stu-id="d8f8b-182">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="d8f8b-183">適用于無理軸之單一 qubit 旋轉的 ru 模式</span><span class="sxs-lookup"><span data-stu-id="d8f8b-183">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="d8f8b-184">在典型的使用案例中，下列作業會針對 Q# Bloch 球體上的無理軸 $ (I + 2I Z) /\sqrt {5} $ 執行旋轉。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-184">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="d8f8b-185">此實作為使用已知的 ru 模式：</span><span class="sxs-lookup"><span data-stu-id="d8f8b-185">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="d8f8b-186">具有範圍內可變變數的 ru 迴圈</span><span class="sxs-lookup"><span data-stu-id="d8f8b-186">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="d8f8b-187">這個範例示範如何使用可變動的變數， `finished` 這是在整個重複執行-修復迴圈的範圍內，而且會在迴圈之前初始化，並在修復步驟中更新。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-187">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="d8f8b-188">不含的 ru`fixup`</span><span class="sxs-lookup"><span data-stu-id="d8f8b-188">RUS without `fixup`</span></span>

<span data-ttu-id="d8f8b-189">此範例顯示不含修復步驟的 ru 迴圈。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-189">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="d8f8b-190">此程式碼是使用和閘道執行重要旋轉閘道 $V _3 = ( \boldone + 2 i Z) /\sqrt $ 的概率電路 {5} `H` `T` 。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-190">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="d8f8b-191">迴圈會平均終止于 $ \frac {8} {5} $ 重複。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="d8f8b-192">如需更多詳細資料，請參閱 qubit unitaries (Paetznick 和 Svore，2014) 的[*重複直到成功：非決定性分解*](https://arxiv.org/abs/1311.1074)。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="d8f8b-193">用來準備量子狀態的 ru</span><span class="sxs-lookup"><span data-stu-id="d8f8b-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="d8f8b-194">最後，以下是 {1} {3} {2} {0} {1} 從 $ \ket +} $ 狀態開始準備量子 state $ \frac {\sqrt} \left ( \sqrt \ket + \right \ket{) $ 的 ru 模式範例。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-194">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="d8f8b-195">這項作業所顯示的重要程式設計功能包括：</span><span class="sxs-lookup"><span data-stu-id="d8f8b-195">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="d8f8b-196">`fixup`迴圈中更複雜的部分，牽涉到量子作業。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-196">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="d8f8b-197">使用 `AssertMeasurementProbability` 語句來確定在程式中特定點測量量子狀態的機率。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-197">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="d8f8b-198">如需和作業的詳細資訊 [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) ，請參閱[測試和調試](xref:microsoft.quantum.guide.testingdebugging)程式。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-198">For more information about the [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
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

<span data-ttu-id="d8f8b-199">如需詳細資訊，請參閱[標準程式庫提供的單元測試範例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)：</span><span class="sxs-lookup"><span data-stu-id="d8f8b-199">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="d8f8b-200">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d8f8b-200">Next steps</span></span>

<span data-ttu-id="d8f8b-201">瞭解中的[測試和調試](xref:microsoft.quantum.guide.testingdebugging) Q# 。</span><span class="sxs-lookup"><span data-stu-id="d8f8b-201">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
