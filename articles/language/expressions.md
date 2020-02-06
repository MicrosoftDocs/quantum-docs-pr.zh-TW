---
title: 運算式 |Microsoft Docs
description: 運算式
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 83fe697aa07a8ab28bd64437c8f5746bc5893b27
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036302"
---
# <a name="expressions"></a><span data-ttu-id="0c000-103">運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="0c000-104">分組</span><span class="sxs-lookup"><span data-stu-id="0c000-104">Grouping</span></span>

<span data-ttu-id="0c000-105">假設有任何運算式，以括弧括住的相同運算式就是相同類型的運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="0c000-106">例如，`(7)` 是 `Int` 運算式，`([1,2,3])` 是 `Int`s 陣列的運算式，而 `((1,2))` 是類型 `(Int, Int)`的運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="0c000-107">在[型別模型](xref:microsoft.quantum.language.type-model#tuple-types)中所描述的簡單值和單一元素元組的等價，會移除 `(6)` 與群組之間的不明確，並 `(6)` 為單一元素的元組。</span><span class="sxs-lookup"><span data-stu-id="0c000-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="0c000-108">符號</span><span class="sxs-lookup"><span data-stu-id="0c000-108">Symbols</span></span>

<span data-ttu-id="0c000-109">系結或指派給型別之值的符號名稱 `'T` 是 `'T`型別的運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="0c000-110">例如，如果符號 `count` 系結至 `5`的整數值，則 `count` 為整數運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="0c000-111">數值運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-111">Numeric Expressions</span></span>

<span data-ttu-id="0c000-112">數值運算式是 `Int`、`BigInt`或 `Double`類型的運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="0c000-113">也就是說，它們可以是整數或浮點數。</span><span class="sxs-lookup"><span data-stu-id="0c000-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="0c000-114">問 # 中的 `Int` 常值與中C#的整數常值相同，不同之處在于不需要尾端的 "l" 或 "l" （或允許）。</span><span class="sxs-lookup"><span data-stu-id="0c000-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="0c000-115">分別支援十六進位和二進位整數和 "0x" 和 "0b" 前置詞。</span><span class="sxs-lookup"><span data-stu-id="0c000-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="0c000-116">Q # 中 `BigInt` 常值與 .NET 中的大整數位符串相同，結尾為 "l" 或 "L"。</span><span class="sxs-lookup"><span data-stu-id="0c000-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="0c000-117">十六進位大整數支援 "0x" 前置詞。</span><span class="sxs-lookup"><span data-stu-id="0c000-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="0c000-118">因此，以下是 `BigInt` 常值的所有有效用法：</span><span class="sxs-lookup"><span data-stu-id="0c000-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="0c000-119">在 Q # 中的 `Double` 常值與中C#的雙常值相同，不同之處在于不需要尾端的 "d" 或 "d" （或允許）。</span><span class="sxs-lookup"><span data-stu-id="0c000-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="0c000-120">假設有任何元素類型的陣列運算式，就可以使用 `Length` 內建函數來形成 `Int` 運算式，並以括弧括住的陣列運算式 `(` 和 `)`。</span><span class="sxs-lookup"><span data-stu-id="0c000-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="0c000-121">例如，如果 `a` 系結至陣列，則 `Length(a)` 為整數運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="0c000-122">如果 `b` 是整數陣列的陣列，則 `Int[][]`，則 `Length(b)` 是 `b`中的子陣列數目，而 `Length(b[1])` 是 `b`中第二個子陣列中的整數數目。</span><span class="sxs-lookup"><span data-stu-id="0c000-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="0c000-123">假設有兩個相同類型的數值運算式，則可以使用二元運算子 `+`、`-`、`*`和 `/` 來形成新的數值運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="0c000-124">新運算式的類型會與組成運算式的類型相同。</span><span class="sxs-lookup"><span data-stu-id="0c000-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="0c000-125">假設有兩個整數運算式，可以使用二元運算子 `^` （乘冪）來形成新的整數運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="0c000-126">同樣地，`^` 可以與兩個雙重運算式搭配使用，以形成新的 double 運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="0c000-127">最後，`^` 可以在左邊使用大整數，並在右邊加上一個整數來形成新的大整數運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="0c000-128">在此情況下，第二個參數必須符合32位;如果不是，則會引發執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="0c000-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="0c000-129">假設有兩個整數或大整數運算式，可以使用 `%` （模數）、`&&&` （位 AND）、`|||` （位 OR）或 `^^^` （位 XOR）運算子來形成新的整數或大整數運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="0c000-130">假設左邊有整數或大整數運算式，而且右邊有整數運算式，則可以使用 `<<<` （算術左移位）或 `>>>` （算術右移位）運算子，來建立與左邊運算式具有相同類型的新運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="0c000-131">轉換作業的第二個參數（移位量）必須大於或等於零;負位移金額的行為未定義。</span><span class="sxs-lookup"><span data-stu-id="0c000-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="0c000-132">任何移位作業的移位量也必須符合32位;如果不是，則會引發執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="0c000-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="0c000-133">如果要移位的數位是整數，則會將位移量 `mod 64`的值加以解讀。也就是說，1的位移和65的位移具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="0c000-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="0c000-134">對於整數和大整數值，移位是算術。</span><span class="sxs-lookup"><span data-stu-id="0c000-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="0c000-135">將負數值向左或右移位會產生負數。</span><span class="sxs-lookup"><span data-stu-id="0c000-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="0c000-136">也就是，將一個步驟向左或向右移位，與分別為乘法或除以2的方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="0c000-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="0c000-137">整數除法和整數模數會遵循與負數相同的行為C#。</span><span class="sxs-lookup"><span data-stu-id="0c000-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="0c000-138">也就是說，`a % b` 一定會具有與 `a`相同的正負號，而且 `b * (a / b) + a % b` 一律會等於 `a`。</span><span class="sxs-lookup"><span data-stu-id="0c000-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="0c000-139">例如，</span><span class="sxs-lookup"><span data-stu-id="0c000-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="0c000-140">5</span><span class="sxs-lookup"><span data-stu-id="0c000-140">5</span></span> | <span data-ttu-id="0c000-141">2</span><span class="sxs-lookup"><span data-stu-id="0c000-141">2</span></span> | <span data-ttu-id="0c000-142">2</span><span class="sxs-lookup"><span data-stu-id="0c000-142">2</span></span> | <span data-ttu-id="0c000-143">1</span><span class="sxs-lookup"><span data-stu-id="0c000-143">1</span></span>
 <span data-ttu-id="0c000-144">5</span><span class="sxs-lookup"><span data-stu-id="0c000-144">5</span></span> | <span data-ttu-id="0c000-145">-2</span><span class="sxs-lookup"><span data-stu-id="0c000-145">-2</span></span> | <span data-ttu-id="0c000-146">-2</span><span class="sxs-lookup"><span data-stu-id="0c000-146">-2</span></span> | <span data-ttu-id="0c000-147">1</span><span class="sxs-lookup"><span data-stu-id="0c000-147">1</span></span>
 <span data-ttu-id="0c000-148">-5</span><span class="sxs-lookup"><span data-stu-id="0c000-148">-5</span></span> | <span data-ttu-id="0c000-149">2</span><span class="sxs-lookup"><span data-stu-id="0c000-149">2</span></span> | <span data-ttu-id="0c000-150">-2</span><span class="sxs-lookup"><span data-stu-id="0c000-150">-2</span></span> | <span data-ttu-id="0c000-151">-1</span><span class="sxs-lookup"><span data-stu-id="0c000-151">-1</span></span>
 <span data-ttu-id="0c000-152">-5</span><span class="sxs-lookup"><span data-stu-id="0c000-152">-5</span></span> | <span data-ttu-id="0c000-153">-2</span><span class="sxs-lookup"><span data-stu-id="0c000-153">-2</span></span> | <span data-ttu-id="0c000-154">2</span><span class="sxs-lookup"><span data-stu-id="0c000-154">2</span></span> | <span data-ttu-id="0c000-155">-1</span><span class="sxs-lookup"><span data-stu-id="0c000-155">-1</span></span>

<span data-ttu-id="0c000-156">大整數除法和模數的運作方式相同。</span><span class="sxs-lookup"><span data-stu-id="0c000-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="0c000-157">假設有任何數值運算式，可以使用 `-` 一元運算子來形成新的運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="0c000-158">新的運算式將與組成運算式的類型相同。</span><span class="sxs-lookup"><span data-stu-id="0c000-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="0c000-159">假設有任何整數或大整數運算式，則可以使用 `~~~` （位補數）一元運算子來形成相同類型的新運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="0c000-160">布林運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-160">Boolean Expressions</span></span>

<span data-ttu-id="0c000-161">這兩個 `Bool` 常值是 `true` 和 `false`。</span><span class="sxs-lookup"><span data-stu-id="0c000-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="0c000-162">假設有兩個相同基本型別的運算式，就可以使用 `==` 和 `!=` 二元運算子來建立 `Bool` 運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="0c000-163">如果兩個運算式相等，則運算式會是 true，否則為 false。</span><span class="sxs-lookup"><span data-stu-id="0c000-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="0c000-164">可能不會比較使用者定義類型的值，只可以比較其未包裝的值。</span><span class="sxs-lookup"><span data-stu-id="0c000-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="0c000-165">例如，使用「解除包裝」運算子 `!` （在 [ [Q # 類型模型] 頁面](xref:microsoft.quantum.language.type-model#user-defined-types)中說明），</span><span class="sxs-lookup"><span data-stu-id="0c000-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="0c000-166">`Qubit` 值的相等比較是否為身分識別相等;也就是說，這兩個運算式是否會識別相同的 qubit。</span><span class="sxs-lookup"><span data-stu-id="0c000-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="0c000-167">這兩個 qubits 的狀態不會由這項比較進行比較、存取、測量或修改。</span><span class="sxs-lookup"><span data-stu-id="0c000-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="0c000-168">`Double` 值的相等比較可能會因為進位效果而誤導。</span><span class="sxs-lookup"><span data-stu-id="0c000-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="0c000-169">例如，`49.0 * (1.0/49.0) != 1.0`。</span><span class="sxs-lookup"><span data-stu-id="0c000-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="0c000-170">假設有兩個數值運算式，可以使用二元運算子 `>`、`<`、`>=`和 `<=` 來建立新的布林運算式，如果第一個運算式分別大於、小於、大於或等於或小於或等於第二個運算式，則會是 true。</span><span class="sxs-lookup"><span data-stu-id="0c000-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="0c000-171">假設有兩個布林運算式，`and` 和 `or` 二元運算子可以用來建立新的布林運算式，如果兩個運算式都是 true，則為 true。</span><span class="sxs-lookup"><span data-stu-id="0c000-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="0c000-172">假設有任何布林運算式，`not` 一元運算子可以用來建立新的布林運算式，如果組成運算式為 false，則為 true。</span><span class="sxs-lookup"><span data-stu-id="0c000-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="0c000-173">字串運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-173">String Expressions</span></span>

<span data-ttu-id="0c000-174">Q # 允許在 `fail` 語句和 `Log` standard 函數中使用字串。</span><span class="sxs-lookup"><span data-stu-id="0c000-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="0c000-175">Q # 中的字串可以是常值或字串插值。</span><span class="sxs-lookup"><span data-stu-id="0c000-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="0c000-176">字串常值類似于大部分語言中的簡單字串常值：以雙引號括住的 Unicode 字元序列，`"`。</span><span class="sxs-lookup"><span data-stu-id="0c000-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="0c000-177">在字串內，`\` 可以使用反斜線字元來將雙引號字元轉義，並插入新行做為 `\n`、以 `\r`傳回的回車，以及做為 `\t`的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0c000-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="0c000-178">例如：</span><span class="sxs-lookup"><span data-stu-id="0c000-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="0c000-179">String 插補的 Q # 語法是C# 7.0 語法的子集;Q # 不支援逐字（多行）字串插值。</span><span class="sxs-lookup"><span data-stu-id="0c000-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="0c000-180">請參閱C#語法的[*字串插值*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。</span><span class="sxs-lookup"><span data-stu-id="0c000-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="0c000-181">插補字串內的運算式遵循 Q # 語法，而C#不是語法。</span><span class="sxs-lookup"><span data-stu-id="0c000-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="0c000-182">任何有效的 Q # 運算式可能會出現在字串插值中。</span><span class="sxs-lookup"><span data-stu-id="0c000-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="0c000-183">Qubit 運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-183">Qubit Expressions</span></span>

<span data-ttu-id="0c000-184">唯一的 `Qubit` 運算式是系結至 `Qubit` 陣列 `Qubit` 值或陣列元素的符號。</span><span class="sxs-lookup"><span data-stu-id="0c000-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="0c000-185">沒有 `Qubit` 常值。</span><span class="sxs-lookup"><span data-stu-id="0c000-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="0c000-186">Pauli 運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-186">Pauli Expressions</span></span>

<span data-ttu-id="0c000-187">四個 `Pauli` 值 `PauliI`、`PauliX`、`PauliY`和 `PauliZ`都是有效的 `Pauli` 運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="0c000-188">除了這以外，唯一的 `Pauli` 運算式是系結至 `Pauli` 陣列 `Pauli` 值或陣列元素的符號。</span><span class="sxs-lookup"><span data-stu-id="0c000-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="0c000-189">結果運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-189">Result Expressions</span></span>

<span data-ttu-id="0c000-190">`One` 和 `Zero`這兩個 `Result` 值都是有效的 `Result` 運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="0c000-191">除了這以外，唯一的 `Result` 運算式是系結至 `Result` 陣列 `Result` 值或陣列元素的符號。</span><span class="sxs-lookup"><span data-stu-id="0c000-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="0c000-192">特別要注意的是，`One` 與整數 `1`不同，而且兩者之間並沒有直接的轉換。</span><span class="sxs-lookup"><span data-stu-id="0c000-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="0c000-193">`Zero` 和 `0`也是如此。</span><span class="sxs-lookup"><span data-stu-id="0c000-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="0c000-194">範圍運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-194">Range Expressions</span></span>

<span data-ttu-id="0c000-195">假設有任何三個 `Int` 運算式 `start`、`step`和 `stop`，`start .. step .. stop` 是一個範圍運算式，其第一個元素為 `start`、第二個元素為 `start+step`、第三個元素為 `start+step+step`等等，直到傳遞 `stop` 為止。</span><span class="sxs-lookup"><span data-stu-id="0c000-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="0c000-196">例如，如果 `step` 是正數且 `stop < start`，範圍可能會是空的。</span><span class="sxs-lookup"><span data-stu-id="0c000-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="0c000-197">如果 `start` 和 `stop` 之間的差異是 `step`的整數倍數，則範圍的最後一個元素會 `stop`。也就是，範圍包含在兩端。</span><span class="sxs-lookup"><span data-stu-id="0c000-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="0c000-198">假設有任何兩個 `Int` 運算式 `start` 和 `stop`，`start .. stop` 就是等於 `start .. 1 .. stop`的範圍運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="0c000-199">請注意，即使 `stop` 小於 `start`，隱含的 `step` 仍為 + 1;在這種情況下，範圍是空的。</span><span class="sxs-lookup"><span data-stu-id="0c000-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="0c000-200">一些範例範圍如下：</span><span class="sxs-lookup"><span data-stu-id="0c000-200">Some example ranges are:</span></span>

- <span data-ttu-id="0c000-201">`1..3` 為1、2、3的範圍。</span><span class="sxs-lookup"><span data-stu-id="0c000-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="0c000-202">`2..2..5` 是2，4的範圍。</span><span class="sxs-lookup"><span data-stu-id="0c000-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="0c000-203">`2..2..6` 為範圍2、4、6。</span><span class="sxs-lookup"><span data-stu-id="0c000-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="0c000-204">`6..-2..2` 為6、4、2的範圍。</span><span class="sxs-lookup"><span data-stu-id="0c000-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="0c000-205">`2..1` 是空的範圍。</span><span class="sxs-lookup"><span data-stu-id="0c000-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="0c000-206">`2..6..7` 為範圍2。</span><span class="sxs-lookup"><span data-stu-id="0c000-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="0c000-207">`2..2..1` 是空的範圍。</span><span class="sxs-lookup"><span data-stu-id="0c000-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="0c000-208">`1..-1..2` 是空的範圍。</span><span class="sxs-lookup"><span data-stu-id="0c000-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="0c000-209">可呼叫的運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-209">Callable Expressions</span></span>

<span data-ttu-id="0c000-210">可呼叫的常值是在編譯範圍中定義的作業或函式的名稱。</span><span class="sxs-lookup"><span data-stu-id="0c000-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="0c000-211">例如，`X` 是參考標準程式庫 `X` 作業的作業常值，而 `Message` 是參考標準程式庫 `Message` 函數的函式常值。</span><span class="sxs-lookup"><span data-stu-id="0c000-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="0c000-212">如果作業支援 `Adjoint` 仿函數，則 `Adjoint op` 是作業運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="0c000-213">同樣地，如果作業支援 `Controlled` 仿函數，則 `Controlled op` 是作業運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="0c000-214">這些運算式的類型是在[函子](xref:microsoft.quantum.language.type-model#functors)中指定。</span><span class="sxs-lookup"><span data-stu-id="0c000-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="0c000-215">函子（`Adjoint` 和 `Controlled`）系結比其他所有運算子更嚴格，但解除包裝運算子 `!` 和使用 `[]`的陣列索引。</span><span class="sxs-lookup"><span data-stu-id="0c000-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="0c000-216">因此，假設作業支援使用的函子，則下列各項都是合法的：</span><span class="sxs-lookup"><span data-stu-id="0c000-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="0c000-217">可呼叫的常值可用來做為值，比方說，是指派給變數或傳遞給另一個可呼叫的。</span><span class="sxs-lookup"><span data-stu-id="0c000-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="0c000-218">在此情況下，如果可呼叫的型別參數為，則必須將它們提供作為可呼叫值的一部分。</span><span class="sxs-lookup"><span data-stu-id="0c000-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="0c000-219">可呼叫的值不能有任何未指定的類型參數。</span><span class="sxs-lookup"><span data-stu-id="0c000-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="0c000-220">例如，如果 `Fun` 是具有簽章 `'T1->Unit`的函數：</span><span class="sxs-lookup"><span data-stu-id="0c000-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="0c000-221">可呼叫的調用運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="0c000-222">假設可呼叫的（作業或函式）運算式，以及可呼叫的簽章之輸入類型的元組運算式，則可以將元組運算式附加至可呼叫的運算式，藉以形成調用運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="0c000-223">調用運算式的類型是可呼叫的簽章的輸出類型。</span><span class="sxs-lookup"><span data-stu-id="0c000-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="0c000-224">例如，如果 `Op` 是具有簽章 `((Int, Qubit) => Double)`的作業，則 `Op(3, qubit1)` 是 `Double`類型的運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="0c000-225">同樣地，如果 `Sin` 是具有簽章 `(Double -> Double)`的函數，則 `Sin(0.1)` 是 `Double`類型的運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="0c000-226">最後，如果 `Builder` 是具有簽章 `(Int -> (Int -> Int))`的函式，則 `Builder(3)` 是從到 Int 的函式。</span><span class="sxs-lookup"><span data-stu-id="0c000-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="0c000-227">叫用可呼叫值運算式的結果時，需要一組額外的括弧括住可呼叫的運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="0c000-228">因此，若要叫用從上一個段落呼叫 `Builder` 的結果，正確的語法為：</span><span class="sxs-lookup"><span data-stu-id="0c000-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="0c000-229">叫用型別參數化可呼叫時，可以在角括弧內指定實際的型別參數 `<`，然後在可呼叫的運算式之後 `>`。</span><span class="sxs-lookup"><span data-stu-id="0c000-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="0c000-230">這通常是不必要的，因為 Q # 編譯器會推斷實際的類型。</span><span class="sxs-lookup"><span data-stu-id="0c000-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="0c000-231">如果未指定型別參數化引數，部分應用程式（如下所示）就需要此參數。</span><span class="sxs-lookup"><span data-stu-id="0c000-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="0c000-232">當將具有不同仿函數支援的作業傳遞至可呼叫的時，它有時也很有用。</span><span class="sxs-lookup"><span data-stu-id="0c000-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="0c000-233">例如，如果 `Func` 有簽章 `('T1, 'T2, 'T1) -> 'T2`，`Op1` 和 `Op2` 會有簽章 `(Qubit[] => Unit is Adj)`，而 `Op3` 具有簽章 `(Qubit[] => Unit)`，以 `Func` 做為第一個引數，`Op1` 做為第二個，然後 `Op2` 為第三個：`Op3`</span><span class="sxs-lookup"><span data-stu-id="0c000-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="0c000-234">類型規格是必要的，因為 `Op3` 和 `Op1` 具有不同的類型，因此編譯器會將此視為不明確的指定。</span><span class="sxs-lookup"><span data-stu-id="0c000-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="0c000-235">部分應用程式</span><span class="sxs-lookup"><span data-stu-id="0c000-235">Partial Application</span></span>

<span data-ttu-id="0c000-236">假設有可呼叫的運算式，就可以將引數的子集提供給可呼叫的，藉以建立新的可呼叫。</span><span class="sxs-lookup"><span data-stu-id="0c000-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="0c000-237">這稱為「_部分應用程式_」。</span><span class="sxs-lookup"><span data-stu-id="0c000-237">This is called _partial application_.</span></span>

<span data-ttu-id="0c000-238">在 Q # 中，部分套用的可呼叫是藉由撰寫一般調用運算式來表示，但針對未指定的引數，則使用底線 `_`。</span><span class="sxs-lookup"><span data-stu-id="0c000-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="0c000-239">產生的可呼叫與基底可呼叫具有相同的結果型別，以及用於作業的相同特製化。</span><span class="sxs-lookup"><span data-stu-id="0c000-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="0c000-240">部分應用程式的輸入類型只是已移除指定引數的原始類型。</span><span class="sxs-lookup"><span data-stu-id="0c000-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="0c000-241">如果在建立部分應用程式時，將可變動的變數當做指定的引數傳遞，則會使用變數目前的值。</span><span class="sxs-lookup"><span data-stu-id="0c000-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="0c000-242">此後變更變數的值不會影響部分應用程式。</span><span class="sxs-lookup"><span data-stu-id="0c000-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="0c000-243">例如，如果 `Op` 具有類型 `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`：</span><span class="sxs-lookup"><span data-stu-id="0c000-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="0c000-244">`Op(5,(_,_))` 具有類型 `(((Qubit,Qubit), Double) => Unit is Adj)`，因此 `Op(5,_)`。</span><span class="sxs-lookup"><span data-stu-id="0c000-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="0c000-245">`Op(_,(_,1.0))` 具有類型 `((Int, (Qubit,Qubit)) => Unit is Adj)`。</span><span class="sxs-lookup"><span data-stu-id="0c000-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="0c000-246">`Op(_,((q1,q2),_))` 具有類型 `((Int,Double) => Unit is Adj)`。</span><span class="sxs-lookup"><span data-stu-id="0c000-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="0c000-247">請注意，我們已在此套用單一元組等價。</span><span class="sxs-lookup"><span data-stu-id="0c000-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="0c000-248">如果部分套用的可呼叫具有編譯器無法推斷的型別參數，則必須在調用網站上提供。</span><span class="sxs-lookup"><span data-stu-id="0c000-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="0c000-249">部分應用程式不能有任何未指定的類型參數。</span><span class="sxs-lookup"><span data-stu-id="0c000-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="0c000-250">例如，如果 `Op` 具有類型 `(('T1, Qubit, 'T1) => Unit : Adjoint)`：</span><span class="sxs-lookup"><span data-stu-id="0c000-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="0c000-251">遞迴</span><span class="sxs-lookup"><span data-stu-id="0c000-251">Recursion</span></span>

<span data-ttu-id="0c000-252">Q # callables 允許直接或間接遞迴。</span><span class="sxs-lookup"><span data-stu-id="0c000-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="0c000-253">也就是說，作業或函式可能會呼叫本身，或呼叫可直接或間接呼叫可呼叫作業的其他調用。</span><span class="sxs-lookup"><span data-stu-id="0c000-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="0c000-254">使用遞迴有兩個重要的批註，不過：</span><span class="sxs-lookup"><span data-stu-id="0c000-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="0c000-255">在作業中使用遞迴可能會干擾特定的優化。</span><span class="sxs-lookup"><span data-stu-id="0c000-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="0c000-256">這可能會對演算法的執行時間產生重大影響。</span><span class="sxs-lookup"><span data-stu-id="0c000-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="0c000-257">在實際的量子裝置上執行時，堆疊空間可能會受到限制，因此深度遞迴可能會導致執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="0c000-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="0c000-258">特別是，Q # 編譯器和執行時間不會識別並優化尾遞迴。</span><span class="sxs-lookup"><span data-stu-id="0c000-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="0c000-259">元組運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-259">Tuple Expressions</span></span>

<span data-ttu-id="0c000-260">元組常值是適當類型的元素運算式序列，並以逗號分隔，並以 `(` 和 `)`括住。</span><span class="sxs-lookup"><span data-stu-id="0c000-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="0c000-261">例如，`(1, One)` 是 `(Int, Result)` 運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="0c000-262">除了常值以外，唯一的元組運算式是系結至元組值的符號、元組陣列的陣列元素，以及傳回元組的可呼叫調用。</span><span class="sxs-lookup"><span data-stu-id="0c000-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="0c000-263">使用者定義型別運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="0c000-264">使用者自訂類型的常值是由類型名稱後面接著類型的基礎元組類型的元組常值所組成。</span><span class="sxs-lookup"><span data-stu-id="0c000-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="0c000-265">例如，如果 `IntPair` 是以 `(Int, Int)`為基礎的使用者定義型別，則 `IntPair(2,3)` 會是該型別的有效常值。</span><span class="sxs-lookup"><span data-stu-id="0c000-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="0c000-266">除了常值以外，使用者定義型別的唯一運算式是系結至該型別、該型別陣列的陣列元素，以及傳回該型別之可呼叫調用的符號。</span><span class="sxs-lookup"><span data-stu-id="0c000-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="0c000-267">解除包裝運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-267">Unwrap Expressions</span></span>

<span data-ttu-id="0c000-268">在 Q # 中，解除包裝運算子是 `!`的尾端驚嘆號。</span><span class="sxs-lookup"><span data-stu-id="0c000-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="0c000-269">例如，如果 `IntPair` 是具有基礎類型 `(Int, Int)`的使用者定義型別，而 `s` 是值 `IntPair(2,3)`的變數，則 `s!` 會 `(2,3)`。</span><span class="sxs-lookup"><span data-stu-id="0c000-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="0c000-270">針對其他使用者定義型別所定義的使用者自訂類型。</span><span class="sxs-lookup"><span data-stu-id="0c000-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="0c000-271">解除包裝運算子可以重複;例如，`s!!` 表示 `s`的雙重解除包裝值。</span><span class="sxs-lookup"><span data-stu-id="0c000-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="0c000-272">因此，如果 `WrappedPair` 是具有基礎類型 `IntPair`的使用者定義型別，而 `t` 是值 `WrappedPair(IntPair(1,2))`的變數，則 `t!!` 會 `(1,2)`。</span><span class="sxs-lookup"><span data-stu-id="0c000-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="0c000-273">`!` 運算子的優先順序高於陣列索引和切割 `[]` 以外的其他所有運算子。</span><span class="sxs-lookup"><span data-stu-id="0c000-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="0c000-274">`!` 和 `[]` 系結 positionally;也就是說，`a[i]![3]` 應該讀取為 `((a[i])!)[3]`：接受 `a`的 `i`第個元素，將它解除包裝，然後取得未包裝值的第3個元素（必須是陣列）。</span><span class="sxs-lookup"><span data-stu-id="0c000-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="0c000-275">`!` 運算子的優先順序有一個可能不明顯的影響。</span><span class="sxs-lookup"><span data-stu-id="0c000-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="0c000-276">如果函式或作業傳回值，因而解除包裝，則函式或作業呼叫必須以括弧括住，讓引數元組系結至呼叫，而不是系結。</span><span class="sxs-lookup"><span data-stu-id="0c000-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="0c000-277">例如，</span><span class="sxs-lookup"><span data-stu-id="0c000-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="0c000-278">陣列運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-278">Array Expressions</span></span>

<span data-ttu-id="0c000-279">陣列常值是一系列的一或多個元素運算式，並以逗號分隔，並以 `[` 和 `]`括住。</span><span class="sxs-lookup"><span data-stu-id="0c000-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="0c000-280">所有元素都必須與相同的型別相容。</span><span class="sxs-lookup"><span data-stu-id="0c000-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="0c000-281">如果一般專案類型是作業或函式類型，所有元素都必須具有相同的輸入和輸出類型。</span><span class="sxs-lookup"><span data-stu-id="0c000-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="0c000-282">陣列的元素類型會支援所有元素所支援的任何函子。</span><span class="sxs-lookup"><span data-stu-id="0c000-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="0c000-283">例如，如果 `Op1`、`Op2`和 `Op3` 都是 `Qubit[] => Unit`的，但 `Op1` 支援 `Adjoint`，`Op2` 支援 `Controlled`，而 `Op3` 同時支援：</span><span class="sxs-lookup"><span data-stu-id="0c000-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="0c000-284">`[Op1, Op2]` 是 `(Qubit[] => Unit)` 作業的陣列。</span><span class="sxs-lookup"><span data-stu-id="0c000-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="0c000-285">`[Op1, Op3]` 是 `(Qubit[] => Unit is Adj)` 作業的陣列。</span><span class="sxs-lookup"><span data-stu-id="0c000-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="0c000-286">`[Op2, Op3]` 是 `(Qubit[] => Unit is Ctl)` 作業的陣列。</span><span class="sxs-lookup"><span data-stu-id="0c000-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="0c000-287">不允許空的陣列常值（`[]`）。</span><span class="sxs-lookup"><span data-stu-id="0c000-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="0c000-288">相反地，使用 `new ★[0]`，其中 `★` 作為適合類型的預留位置，可讓建立所需長度為零的陣列。</span><span class="sxs-lookup"><span data-stu-id="0c000-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="0c000-289">假設有兩個相同類型的陣列，則可以使用 binary `+` 運算子來形成新陣列，這是兩個數組的串連。</span><span class="sxs-lookup"><span data-stu-id="0c000-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="0c000-290">例如，`[1,2,3] + [4,5,6]` 是 `[1,2,3,4,5,6]`。</span><span class="sxs-lookup"><span data-stu-id="0c000-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="0c000-291">陣列建立</span><span class="sxs-lookup"><span data-stu-id="0c000-291">Array Creation</span></span>

<span data-ttu-id="0c000-292">假設有一個型別和一個 `Int` 運算式，就可以使用 `new` 運算子來配置指定大小的新陣列。</span><span class="sxs-lookup"><span data-stu-id="0c000-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="0c000-293">例如，`new Int[i+1]` 會配置具有 `i+1` 元素的新 `Int` 陣列。</span><span class="sxs-lookup"><span data-stu-id="0c000-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="0c000-294">新陣列的元素會初始化為與類型相關的預設值。</span><span class="sxs-lookup"><span data-stu-id="0c000-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="0c000-295">在大部分情況下，這會是零的部分變化。</span><span class="sxs-lookup"><span data-stu-id="0c000-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="0c000-296">對於實體參考的 qubits 和 callables 而言，沒有合理的預設值。</span><span class="sxs-lookup"><span data-stu-id="0c000-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="0c000-297">因此，對於這些類型，預設值為不正確參考，無法使用而不會造成執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="0c000-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="0c000-298">這類似于C#或 JAVA 等語言中的 null 參考。</span><span class="sxs-lookup"><span data-stu-id="0c000-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="0c000-299">包含 qubits 或 callables 的陣列必須使用非預設值正確地初始化，才可以安全地使用它們的元素。</span><span class="sxs-lookup"><span data-stu-id="0c000-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="0c000-300">您可以在 <xref:microsoft.quantum.arrays>中找到適當的初始化常式。</span><span class="sxs-lookup"><span data-stu-id="0c000-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="0c000-301">每種類型的預設值為：</span><span class="sxs-lookup"><span data-stu-id="0c000-301">The default values for each type are:</span></span>

<span data-ttu-id="0c000-302">類型</span><span class="sxs-lookup"><span data-stu-id="0c000-302">Type</span></span> | <span data-ttu-id="0c000-303">預設</span><span class="sxs-lookup"><span data-stu-id="0c000-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="0c000-304">_不正確 qubit_</span><span class="sxs-lookup"><span data-stu-id="0c000-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="0c000-305">空白範圍，`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="0c000-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="0c000-306">_可呼叫無效_</span><span class="sxs-lookup"><span data-stu-id="0c000-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="0c000-307">元組類型會依元素初始化。</span><span class="sxs-lookup"><span data-stu-id="0c000-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="0c000-308">不規則陣列</span><span class="sxs-lookup"><span data-stu-id="0c000-308">Jagged Arrays</span></span>

<span data-ttu-id="0c000-309">不規則陣列（有時稱為「陣列陣列」）是其元素為數組的陣列。</span><span class="sxs-lookup"><span data-stu-id="0c000-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="0c000-310">不規則陣列的元素可以是不同的大小。</span><span class="sxs-lookup"><span data-stu-id="0c000-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="0c000-311">下列範例顯示如何宣告和初始化代表乘法資料表的不規則陣列。</span><span class="sxs-lookup"><span data-stu-id="0c000-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {

    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```


### <a name="array-slices"></a><span data-ttu-id="0c000-312">陣列配量</span><span class="sxs-lookup"><span data-stu-id="0c000-312">Array Slices</span></span>

<span data-ttu-id="0c000-313">假設有陣列運算式和 `Range` 運算式，則可以使用 `[` 和 `]` 陣列配量運算子來形成新的運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="0c000-314">新的運算式會與陣列具有相同的類型，而且會包含依 `Range`所定義的順序，以 `Range`的元素編制索引的陣列專案。</span><span class="sxs-lookup"><span data-stu-id="0c000-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="0c000-315">例如，如果 `a` 系結至 `Double`s 的陣列，則 `a[3..-1..0]` 是 `Double[]` 運算式，其中包含 `a` 的前四個元素，但順序與 `a`中出現的相反。</span><span class="sxs-lookup"><span data-stu-id="0c000-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="0c000-316">如果 `Range` 是空的，則產生的陣列配量會是長度為零的。</span><span class="sxs-lookup"><span data-stu-id="0c000-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="0c000-317">如果陣列運算式不是簡單的識別碼，則必須將它括在括弧內，才能進行配量。</span><span class="sxs-lookup"><span data-stu-id="0c000-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="0c000-318">例如，如果 `a` 和 `b` 都是 `Int`的陣列，則串連中的配量會表示為：</span><span class="sxs-lookup"><span data-stu-id="0c000-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="0c000-319">Q # 中的所有陣列都是以零為基底。</span><span class="sxs-lookup"><span data-stu-id="0c000-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="0c000-320">也就是說，陣列 `a` 的第一個元素一律會 `a[0]`。</span><span class="sxs-lookup"><span data-stu-id="0c000-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="0c000-321">從0.8 版開始，我們支援範圍切割的內容相關運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="0c000-322">特別的是，範圍的開始和結束值可能會在範圍切割運算式的內容中省略。</span><span class="sxs-lookup"><span data-stu-id="0c000-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="0c000-323">在這種情況下，編譯器將會套用下列規則，以推斷範圍的預期分隔符號。</span><span class="sxs-lookup"><span data-stu-id="0c000-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="0c000-324">例如，如果省略範圍起始值，則推斷的起始值</span><span class="sxs-lookup"><span data-stu-id="0c000-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="0c000-325">如果未指定任何步驟，或指定的步驟是正數，則為零，而</span><span class="sxs-lookup"><span data-stu-id="0c000-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="0c000-326">如果指定的步驟是負數，則為已切割陣列的長度減一。</span><span class="sxs-lookup"><span data-stu-id="0c000-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="0c000-327">如果省略範圍結束值，則推斷的結束值</span><span class="sxs-lookup"><span data-stu-id="0c000-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="0c000-328">這是已切割陣列的長度減一，如果未指定任何步驟，或指定的步驟是正數，則為，</span><span class="sxs-lookup"><span data-stu-id="0c000-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="0c000-329">如果指定的步驟是負數，則為零。</span><span class="sxs-lookup"><span data-stu-id="0c000-329">is zero if the specified step is negative.</span></span> 

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

## <a name="array-element-expressions"></a><span data-ttu-id="0c000-330">陣列元素運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-330">Array Element Expressions</span></span>

<span data-ttu-id="0c000-331">假設有陣列運算式和 `Int` 運算式，則可以使用 `[` 和 `]` 陣列元素運算子來形成新的運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="0c000-332">新的運算式將與陣列的元素類型相同。</span><span class="sxs-lookup"><span data-stu-id="0c000-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="0c000-333">例如，如果 `a` 系結至 `Double`s 的陣列，則 `a[4]` 是 `Double` 運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="0c000-334">如果陣列運算式不是簡單的識別碼，則必須將它括在括弧內，才能選取元素。</span><span class="sxs-lookup"><span data-stu-id="0c000-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="0c000-335">例如，如果 `a` 和 `b` 都是 `Int`的陣列，則串連中的元素會表示為：</span><span class="sxs-lookup"><span data-stu-id="0c000-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="0c000-336">Q # 中的所有陣列都是以零為基底。</span><span class="sxs-lookup"><span data-stu-id="0c000-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="0c000-337">也就是說，陣列 `a` 的第一個元素一律會 `a[0]`。</span><span class="sxs-lookup"><span data-stu-id="0c000-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="0c000-338">複製和更新運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="0c000-339">您可以透過複製和更新運算式，從現有的陣列建立新的陣列。</span><span class="sxs-lookup"><span data-stu-id="0c000-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="0c000-340">複製和更新運算式是格式為 `expression1 w/ expression2 <- expression3`的運算式，其中 `expression1` 必須是某些類型 `T`的類型 `T[]`。</span><span class="sxs-lookup"><span data-stu-id="0c000-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="0c000-341">第二個 `expression2` 會定義相較于 `expression1` 中的陣列，要修改之元素的索引，而且必須是 `Int` 類型或 `Range`類型的類型。</span><span class="sxs-lookup"><span data-stu-id="0c000-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="0c000-342">如果 `expression2` 的類型為 `Int`，`expression3` 必須是 `T`類型。</span><span class="sxs-lookup"><span data-stu-id="0c000-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="0c000-343">如果 `expression2` 的類型為 `Range`，`expression3` 必須是 `T[]`類型。</span><span class="sxs-lookup"><span data-stu-id="0c000-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="0c000-344">「複製並更新」運算式 `arr w/ idx <- value` 會在 `arr`中，以所有設定為對應元素的專案來建立新的陣列，但 `idx`的元素除外，其設定為 `value`中的一個專案。</span><span class="sxs-lookup"><span data-stu-id="0c000-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="0c000-345">例如，如果 `arr` 包含 `[0,1,2,3]`的陣列，則</span><span class="sxs-lookup"><span data-stu-id="0c000-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="0c000-346">`arr w/ 0 <- 10` 是陣列 `[10,1,2,3]`。</span><span class="sxs-lookup"><span data-stu-id="0c000-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="0c000-347">`arr w/ 2 <- 10` 是陣列 `[0,1,10,3]`。</span><span class="sxs-lookup"><span data-stu-id="0c000-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="0c000-348">`arr w/ 0..2..3 <- [10,12]` 是陣列 `[10,1,12,3]`。</span><span class="sxs-lookup"><span data-stu-id="0c000-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="0c000-349">使用者定義類型中的命名專案有類似的運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="0c000-350">請考慮類型的範例</span><span class="sxs-lookup"><span data-stu-id="0c000-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="0c000-351">如果 `c` 包含 `Complex(1.,-1.)`類型的值，則 `c w/ Re <- 0.` 是評估為 `Complex(0.,-1.)`之類型 `Complex` 的運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="0c000-352">條件運算式</span><span class="sxs-lookup"><span data-stu-id="0c000-352">Conditional Expressions</span></span>

<span data-ttu-id="0c000-353">假設有兩個相同類型和布林運算式的其他運算式，則可以使用問號 `?` 和分隔號 `|`來形成條件運算式。</span><span class="sxs-lookup"><span data-stu-id="0c000-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="0c000-354">例如，`a==b ? c | d`。</span><span class="sxs-lookup"><span data-stu-id="0c000-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="0c000-355">在此範例中，如果 `a==b` 為 true，則會 `c` 條件運算式的值，而如果為 false，則 `d`。</span><span class="sxs-lookup"><span data-stu-id="0c000-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="0c000-356">這兩個運算式可能會評估為具有相同輸入和輸出但支援不同函子的作業。</span><span class="sxs-lookup"><span data-stu-id="0c000-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="0c000-357">在此情況下，條件運算式的類型是具有這些輸入和輸出的作業，可支援這兩個運算式所支援的任何函子。</span><span class="sxs-lookup"><span data-stu-id="0c000-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="0c000-358">例如，如果 `Op1`、`Op2`和 `Op3` 都是 `Qubit[]=>Unit`的，但 `Op1` 支援 `Adjoint`，`Op2` 支援 `Controlled`，而 `Op3` 同時支援：</span><span class="sxs-lookup"><span data-stu-id="0c000-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="0c000-359">`flag ? Op1 | Op2` 是 `(Qubit[] => Unit)` 作業。</span><span class="sxs-lookup"><span data-stu-id="0c000-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="0c000-360">`flag ? Op1 | Op3` 是 `(Qubit[] => Unit is Adj)` 作業。</span><span class="sxs-lookup"><span data-stu-id="0c000-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="0c000-361">`flag ? Op2 | Op3` 是 `(Qubit[] => Unit is Ctl)` 作業。</span><span class="sxs-lookup"><span data-stu-id="0c000-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="0c000-362">如果兩個可能的結果運算式中有一個包含函式或作業呼叫，只有當該結果是將成為呼叫值的呼叫時，才會進行該呼叫。</span><span class="sxs-lookup"><span data-stu-id="0c000-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="0c000-363">例如，在案例中 `a==b ? C(qs) | D(qs)`，如果 `a==b` 為 true，則會叫用 `C` 作業，如果是 false，則只會叫用 `D`。</span><span class="sxs-lookup"><span data-stu-id="0c000-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="0c000-364">這類似于其他語言的簡短運算。</span><span class="sxs-lookup"><span data-stu-id="0c000-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="0c000-365">運算子優先順序</span><span class="sxs-lookup"><span data-stu-id="0c000-365">Operator Precedence</span></span>

<span data-ttu-id="0c000-366">除了 `^`以外，所有二元運算子都是右向關聯。</span><span class="sxs-lookup"><span data-stu-id="0c000-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="0c000-367">括弧、`[` 和 `]`，針對陣列切割和索引編制，請在任何運算子之前系結。</span><span class="sxs-lookup"><span data-stu-id="0c000-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="0c000-368">函子在陣列索引之後，但在其他所有運算子之前，會 `Adjoint` 和 `Controlled` 系結。</span><span class="sxs-lookup"><span data-stu-id="0c000-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="0c000-369">運算和函式呼叫的括弧也會系結在任何運算子之前，但是在陣列索引和函子之後。</span><span class="sxs-lookup"><span data-stu-id="0c000-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="0c000-370">依優先順序排列的運算子，從最高到最低：</span><span class="sxs-lookup"><span data-stu-id="0c000-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="0c000-371">運算子</span><span class="sxs-lookup"><span data-stu-id="0c000-371">Operator</span></span> | <span data-ttu-id="0c000-372">Arity</span><span class="sxs-lookup"><span data-stu-id="0c000-372">Arity</span></span> | <span data-ttu-id="0c000-373">描述</span><span class="sxs-lookup"><span data-stu-id="0c000-373">Description</span></span> | <span data-ttu-id="0c000-374">運算元類型</span><span class="sxs-lookup"><span data-stu-id="0c000-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="0c000-375">尾端 `!`</span><span class="sxs-lookup"><span data-stu-id="0c000-375">trailing `!`</span></span> | <span data-ttu-id="0c000-376">一元 (Unary)</span><span class="sxs-lookup"><span data-stu-id="0c000-376">Unary</span></span> | <span data-ttu-id="0c000-377">解除包裝</span><span class="sxs-lookup"><span data-stu-id="0c000-377">Unwrap</span></span> | <span data-ttu-id="0c000-378">任何使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="0c000-378">Any user-defined type</span></span>
 <span data-ttu-id="0c000-379">`-`、`~~~`、`not`</span><span class="sxs-lookup"><span data-stu-id="0c000-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="0c000-380">一元 (Unary)</span><span class="sxs-lookup"><span data-stu-id="0c000-380">Unary</span></span> | <span data-ttu-id="0c000-381">數值負數、位補數、邏輯否定</span><span class="sxs-lookup"><span data-stu-id="0c000-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="0c000-382">`Int`、`BigInt` 或 `Double` `-`、`Int` 或 `BigInt` `~~~`、`Bool``not`</span><span class="sxs-lookup"><span data-stu-id="0c000-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="0c000-383">Binary</span><span class="sxs-lookup"><span data-stu-id="0c000-383">Binary</span></span> | <span data-ttu-id="0c000-384">整數乘冪</span><span class="sxs-lookup"><span data-stu-id="0c000-384">Integer power</span></span> | <span data-ttu-id="0c000-385">`Int` 或 `BigInt` 作為基底，`Int` 指數</span><span class="sxs-lookup"><span data-stu-id="0c000-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="0c000-386">`/`、`*`、`%`</span><span class="sxs-lookup"><span data-stu-id="0c000-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="0c000-387">Binary</span><span class="sxs-lookup"><span data-stu-id="0c000-387">Binary</span></span> | <span data-ttu-id="0c000-388">除法、乘法、integer 模數</span><span class="sxs-lookup"><span data-stu-id="0c000-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="0c000-389">`Int`、`BigInt` 或 `Double` `/` 和 `*`、`Int` 或 `BigInt` `%`</span><span class="sxs-lookup"><span data-stu-id="0c000-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="0c000-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="0c000-390">`+`, `-`</span></span> | <span data-ttu-id="0c000-391">Binary</span><span class="sxs-lookup"><span data-stu-id="0c000-391">Binary</span></span> | <span data-ttu-id="0c000-392">加法或字串和陣列串連，減法</span><span class="sxs-lookup"><span data-stu-id="0c000-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="0c000-393">`Int`、`BigInt` 或 `Double`，此外 `String` 或任何 `+` 的陣列類型</span><span class="sxs-lookup"><span data-stu-id="0c000-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="0c000-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="0c000-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="0c000-395">Binary</span><span class="sxs-lookup"><span data-stu-id="0c000-395">Binary</span></span> | <span data-ttu-id="0c000-396">左 shift、right shift</span><span class="sxs-lookup"><span data-stu-id="0c000-396">Left shift, right shift</span></span> | <span data-ttu-id="0c000-397">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="0c000-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="0c000-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="0c000-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="0c000-399">Binary</span><span class="sxs-lookup"><span data-stu-id="0c000-399">Binary</span></span> | <span data-ttu-id="0c000-400">小於、小於或等於、大於、大於、等於或相等的比較</span><span class="sxs-lookup"><span data-stu-id="0c000-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="0c000-401">`Int`、`BigInt` 或 `Double`</span><span class="sxs-lookup"><span data-stu-id="0c000-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="0c000-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="0c000-402">`==`, `!=`</span></span> | <span data-ttu-id="0c000-403">Binary</span><span class="sxs-lookup"><span data-stu-id="0c000-403">Binary</span></span> | <span data-ttu-id="0c000-404">等於、不等於比較</span><span class="sxs-lookup"><span data-stu-id="0c000-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="0c000-405">任何基本類型</span><span class="sxs-lookup"><span data-stu-id="0c000-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="0c000-406">Binary</span><span class="sxs-lookup"><span data-stu-id="0c000-406">Binary</span></span> | <span data-ttu-id="0c000-407">位元 AND</span><span class="sxs-lookup"><span data-stu-id="0c000-407">Bitwise AND</span></span> | <span data-ttu-id="0c000-408">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="0c000-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="0c000-409">Binary</span><span class="sxs-lookup"><span data-stu-id="0c000-409">Binary</span></span> | <span data-ttu-id="0c000-410">位元 XOR</span><span class="sxs-lookup"><span data-stu-id="0c000-410">Bitwise XOR</span></span> | <span data-ttu-id="0c000-411">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="0c000-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="0c000-412">Binary</span><span class="sxs-lookup"><span data-stu-id="0c000-412">Binary</span></span> | <span data-ttu-id="0c000-413">位元 OR</span><span class="sxs-lookup"><span data-stu-id="0c000-413">Bitwise OR</span></span> | <span data-ttu-id="0c000-414">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="0c000-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="0c000-415">Binary</span><span class="sxs-lookup"><span data-stu-id="0c000-415">Binary</span></span> | <span data-ttu-id="0c000-416">邏輯 AND</span><span class="sxs-lookup"><span data-stu-id="0c000-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="0c000-417">Binary</span><span class="sxs-lookup"><span data-stu-id="0c000-417">Binary</span></span> | <span data-ttu-id="0c000-418">邏輯 OR</span><span class="sxs-lookup"><span data-stu-id="0c000-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="0c000-419">Binary/三元</span><span class="sxs-lookup"><span data-stu-id="0c000-419">Binary/Ternary</span></span> | <span data-ttu-id="0c000-420">Range 運算子</span><span class="sxs-lookup"><span data-stu-id="0c000-420">Range operator</span></span> | `Int`
 <span data-ttu-id="0c000-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="0c000-421">`?` `|`</span></span> | <span data-ttu-id="0c000-422">三元</span><span class="sxs-lookup"><span data-stu-id="0c000-422">Ternary</span></span> | <span data-ttu-id="0c000-423">條件式</span><span class="sxs-lookup"><span data-stu-id="0c000-423">Conditional</span></span> | <span data-ttu-id="0c000-424">左側的 `Bool`</span><span class="sxs-lookup"><span data-stu-id="0c000-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="0c000-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="0c000-425">`w/` `<-`</span></span> | <span data-ttu-id="0c000-426">三元</span><span class="sxs-lookup"><span data-stu-id="0c000-426">Ternary</span></span> | <span data-ttu-id="0c000-427">複製和更新</span><span class="sxs-lookup"><span data-stu-id="0c000-427">Copy-and-update</span></span> | <span data-ttu-id="0c000-428">請參閱[複製和更新運算式](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="0c000-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
