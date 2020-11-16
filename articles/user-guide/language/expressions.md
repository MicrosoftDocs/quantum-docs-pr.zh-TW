---
title: '中的運算式 Q#'
description: '瞭解如何在中指定、參考和合併常數、變數、運算子、作業和函數 Q# 。'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: e95a7cb9b74136ef9a6f51b4bbc32d1d93c43a0d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691598"
---
# <a name="expressions-in-no-locq"></a><span data-ttu-id="9ff9f-103">中的運算式 Q#</span><span class="sxs-lookup"><span data-stu-id="9ff9f-103">Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="9ff9f-104">數值運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-104">Numeric Expressions</span></span>

<span data-ttu-id="9ff9f-105">數值運算式是、或類型的運算式 `Int` `BigInt` `Double` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="9ff9f-106">亦即，它們可以是整數或浮點數。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="9ff9f-107">`Int` 中的常值 Q# 會寫入為一系列的數位。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="9ff9f-108">以和前置詞分別支援和寫入十六進位和二進位整數 `0x` `0b` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="9ff9f-109">`BigInt` 中的常值 Q# 具有尾端或後置詞 `l` `L` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="9ff9f-110">以 "0x" 前置詞支援和寫入十六進位大整數。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="9ff9f-111">因此，下列是常值的所有有效用法 `BigInt` ：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="9ff9f-112">`Double` 中的常 Q# 值是使用小數位數寫入的浮點數。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="9ff9f-113">您可以使用或不含小數點、或 `.` 以 ' e ' 或 ' e (' 表示的指數部分來撰寫它們，但在這種情況下，只有可能的負號和小數位數是有效的) 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="9ff9f-114">以下是有效的 `Double` 常值： `0.0` 、 `1.2e5` 、 `1e-5` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="9ff9f-115">如果有任何專案類型的陣列運算式，您可以使用內 `Int` 建函數來形成運算式 [`Length`](xref:Microsoft.Quantum.Core.Length) ，並以括弧括住陣列運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:Microsoft.Quantum.Core.Length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="9ff9f-116">例如，如果系結 `a` 至陣列，則 `Length(a)` 為整數運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="9ff9f-117">如果 `b` 是整數陣列的陣列， `Int[][]` 則 `Length(b)` 為中的子陣列數目， `b` 而 `Length(b[1])` 是中第二個子陣列中的整數數目 `b` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="9ff9f-118">假設有兩個相同類型的數值運算式，則二元運算子 `+` 、、 `-` 和可用 `*` `/` 來形成新的數值運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="9ff9f-119">新運算式的型別與組成運算式的類型相同。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="9ff9f-120">假設有兩個整數運算式，請使用二元運算子 `^` (power) 來形成新的整數運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="9ff9f-121">同樣地，您也可以使用 `^` with 兩個雙精度浮點數運算式來形成新的雙精度浮點數運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="9ff9f-122">最後，您可以使用 `^` 左邊的大整數和右邊的整數來形成新的大整數運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="9ff9f-123">在此情況下，第二個參數必須符合32位;如果沒有，則會引發執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="9ff9f-124">假設有兩個整數或大整數運算式，則會使用 `%` (模數) 、 `&&&` (位 and) 、 `|||` (位 or) 或 `^^^` (位 XOR) 運算子來形成新的整數或大整數運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="9ff9f-125">指定左邊的整數或大整數運算式，以及右邊的整數運算式時，請使用 `<<<` (算術左移) 或 `>>>` (算術右移) 運算子來建立新的運算式，其類型與左邊的運算式相同。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="9ff9f-126">第二個參數 (移位量) 的移位量必須大於或等於零;負移位數量的行為未定義。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="9ff9f-127">Shift 作業的移位量也必須符合32位;如果沒有，則會引發執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="9ff9f-128">如果移位的數位是整數，則會解釋移位量，也 `mod 64` 就是1與65的位移具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="9ff9f-129">針對整數和大整數值，移位是算術。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="9ff9f-130">將負數值向左或向右移位會產生負數。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="9ff9f-131">亦即，將一個步驟向左或向右移動，會分別與相乘或除以2相同。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="9ff9f-132">整數除法和整數模數會遵循與 c # 相同的負數行為。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span> <span data-ttu-id="9ff9f-133">也就是說， `a % b` 一律具有相同的正負號 `a` ，且 `b * (a / b) + a % b` 一律等於 `a` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span> <span data-ttu-id="9ff9f-134">例如：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-134">For example:</span></span>

|`A` | `B` | `A / B` | `A % B`|
|:---------:|:----------:|:---------:|:---------:|
| <span data-ttu-id="9ff9f-135">5</span><span class="sxs-lookup"><span data-stu-id="9ff9f-135">5</span></span> | <span data-ttu-id="9ff9f-136">2</span><span class="sxs-lookup"><span data-stu-id="9ff9f-136">2</span></span> | <span data-ttu-id="9ff9f-137">2</span><span class="sxs-lookup"><span data-stu-id="9ff9f-137">2</span></span> | <span data-ttu-id="9ff9f-138">1</span><span class="sxs-lookup"><span data-stu-id="9ff9f-138">1</span></span> |
| <span data-ttu-id="9ff9f-139">5</span><span class="sxs-lookup"><span data-stu-id="9ff9f-139">5</span></span> | <span data-ttu-id="9ff9f-140">-2</span><span class="sxs-lookup"><span data-stu-id="9ff9f-140">-2</span></span> | <span data-ttu-id="9ff9f-141">-2</span><span class="sxs-lookup"><span data-stu-id="9ff9f-141">-2</span></span> | <span data-ttu-id="9ff9f-142">1</span><span class="sxs-lookup"><span data-stu-id="9ff9f-142">1</span></span> |
| <span data-ttu-id="9ff9f-143">-5</span><span class="sxs-lookup"><span data-stu-id="9ff9f-143">-5</span></span> | <span data-ttu-id="9ff9f-144">2</span><span class="sxs-lookup"><span data-stu-id="9ff9f-144">2</span></span> | <span data-ttu-id="9ff9f-145">-2</span><span class="sxs-lookup"><span data-stu-id="9ff9f-145">-2</span></span> | <span data-ttu-id="9ff9f-146">-1</span><span class="sxs-lookup"><span data-stu-id="9ff9f-146">-1</span></span> |
| <span data-ttu-id="9ff9f-147">-5</span><span class="sxs-lookup"><span data-stu-id="9ff9f-147">-5</span></span> | <span data-ttu-id="9ff9f-148">-2</span><span class="sxs-lookup"><span data-stu-id="9ff9f-148">-2</span></span> | <span data-ttu-id="9ff9f-149">2</span><span class="sxs-lookup"><span data-stu-id="9ff9f-149">2</span></span> | <span data-ttu-id="9ff9f-150">-1</span><span class="sxs-lookup"><span data-stu-id="9ff9f-150">-1</span></span> |

<span data-ttu-id="9ff9f-151">大整數除法和模數運算的運作方式相同。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="9ff9f-152">假設有任何數值運算式，您可以使用一元運算子來形成新的運算式 `-` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="9ff9f-153">新的運算式與組成運算式的類型相同。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="9ff9f-154">假設有任何整數或大整數運算式，您可以使用 `~~~` (位補數) 一元運算子來形成相同型別的新運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="9ff9f-155">布林運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-155">Boolean Expressions</span></span>

<span data-ttu-id="9ff9f-156">這兩個 `Bool` 常值為 `true` 和 `false` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="9ff9f-157">假設有兩個相同基本型別的運算式， `==` 就可以 `!=` 使用和二元運算子來建立 `Bool` 運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="9ff9f-158">如果兩個運算式相等，則運算式為 true，否則為 false。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="9ff9f-159">使用者自訂類型的值可能不會進行比較，只能比較其未包裝的值。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="9ff9f-160">例如，使用「解除包裝」運算子 `!` (在) 的[類型 Q# ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)中詳細說明。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="9ff9f-161">值的相等比較是身分識別 `Qubit` 相等，也就是兩個運算式是否識別相同的量子位。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="9ff9f-162">這兩個量子位的狀態不會進行比較、存取、測量或修改。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="9ff9f-163">值的相等比較 `Double` 可能會因為四捨五入效果而產生誤導。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="9ff9f-164">例如： `49.0 * (1.0/49.0) != 1.0` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="9ff9f-165">假設有兩個數值運算式，則二元運算子 `>` 、 `<` 、和可用 `>=` `<=` 來建立新的布林運算式，如果第一個運算式分別大於、小於、大於或等於或小於或等於第二個運算式，則為 true。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="9ff9f-166">假設有兩個布林運算式，請使用 `and` 二元運算子來建立新的布林運算式，如果兩個運算式都是 true，則為 true。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="9ff9f-167">同樣地， `or` 如果兩個運算式中的任一個都是 true，則使用運算子會建立一個 true 的運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="9ff9f-168">假設有任何布林運算式， `not` 一元運算子可用來建立新的布林運算式，如果組成運算式為 false，則為 true。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="9ff9f-169">字串運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-169">String expressions</span></span>

<span data-ttu-id="9ff9f-170">Q# 允許在語句中使用字串 `fail` (在 [控制流程](xref:microsoft.quantum.guide.controlflow#fail-statement)) 和標準函式中所述 [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) standard function.</span></span> <span data-ttu-id="9ff9f-171">後者的特定行為取決於使用的模擬器，但通常會在程式期間呼叫時，將訊息寫入主機主控台 Q# 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="9ff9f-172">中的字串 Q# 是常值或字串插值。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="9ff9f-173">字串常值類似于大部分語言中的簡單字串常值：以雙引號括住的 Unicode 字元序列 `" "` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="9ff9f-174">在字串內，請使用反斜線字元 `\` 來將雙引號字元 (`\"`) ，或插入新行 ( ) 、換行字元 `\n` () ，或索引標籤 `\r` (`\t`) 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="9ff9f-175">例如：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="9ff9f-176">插入字串</span><span class="sxs-lookup"><span data-stu-id="9ff9f-176">Interpolated strings</span></span>

<span data-ttu-id="9ff9f-177">Q#字串插補的語法是 c # 語法的子集。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="9ff9f-178">以下是其相關的重點 Q# ：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="9ff9f-179">若要將字串常值識別為插入字串，請在其前面加上 `$` 符號。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="9ff9f-180">`$`與開始字串常值的之間不能有空白字元 `"` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="9ff9f-181">以下是使用 [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) 函數將測量結果與其他運算式一起寫入至主控台的基本範例 Q# 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-181">The following is a basic example using the [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="9ff9f-182">任何有效 Q# 的運算式可能會出現在字串插值中。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="9ff9f-183">字串插值中的運算式會遵循 Q# 語法，而不是 c # 語法。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="9ff9f-184">最顯著的差異在於不 Q# 支援逐字 (多行) 插入字串。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="9ff9f-185">如需 c # 語法的詳細資訊，請參閱插入 [*字串*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="9ff9f-186">範圍運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-186">Range Expressions</span></span>

<span data-ttu-id="9ff9f-187">假設有三個 `Int` 運算式 `start` 、 `step` 和 `stop` ，則運算式 `start .. step .. stop` 是一個範圍運算式，其第一個元素為 `start` ，第二個元素是 `start+step` ，第三個元素是 `start+step+step` ，依此類推，直到您通過為止 `stop` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="9ff9f-188">例如，如果是正數和，範圍可能是空的 `step` `stop < start` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="9ff9f-189">範圍在兩端都包含在內。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="9ff9f-190">也就是說，如果和之間的差異 `start` `stop` 是的整數倍數，則 `step` 範圍的最後一個專案會是 `stop` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="9ff9f-191">假設有兩個 `Int` 運算式 `start` 和，則 `stop` 運算式 `start .. stop` 是等於的範圍運算式 `start .. 1 .. stop` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="9ff9f-192">請注意， `step` 即使 `stop` 小於 `start` ; 在這種情況下，隱含是 + 1，範圍是空的。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="9ff9f-193">部分範例範圍如下：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-193">Some example ranges are:</span></span>

- <span data-ttu-id="9ff9f-194">`1..3` 是範圍1、2、3。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="9ff9f-195">`2..2..5` 為範圍2、4。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="9ff9f-196">`2..2..6` 為範圍2、4、6。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="9ff9f-197">`6..-2..2` 為6、4、2的範圍。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="9ff9f-198">`2..1` 是空的範圍。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="9ff9f-199">`2..6..7` 為範圍2。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="9ff9f-200">`2..2..1` 是空的範圍。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="9ff9f-201">`1..-1..2` 是空的範圍。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="9ff9f-202">量子位運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-202">Qubit Expressions</span></span>

<span data-ttu-id="9ff9f-203">唯一的 `Qubit` 運算式是系結至 `Qubit` 陣列值或陣列元素的符號 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="9ff9f-204">沒有常值 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="9ff9f-205">Pauli 運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-205">Pauli Expressions</span></span>

<span data-ttu-id="9ff9f-206">四個 `Pauli` 值（、、 `PauliI` `PauliX` `PauliY` 和 `PauliZ` ）都是有效的 `Pauli` 運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="9ff9f-207">除了這樣，唯一的 `Pauli` 運算式是系結至 `Pauli` 陣列值或陣列元素的符號 `Pauli` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="9ff9f-208">結果運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-208">Result Expressions</span></span>

<span data-ttu-id="9ff9f-209">這兩個 `Result` 值 `One` `Zero` 都是有效的 `Result` 運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="9ff9f-210">除了這樣，唯一的 `Result` 運算式是系結至 `Result` 陣列值或陣列元素的符號 `Result` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="9ff9f-211">請特別注意，與 `One` 整數不同的是 `1` ，它們之間並沒有直接的轉換。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="9ff9f-212">和也是如此 `Zero` `0` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="9ff9f-213">元組運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-213">Tuple Expressions</span></span>

<span data-ttu-id="9ff9f-214">元組常值是適當類型的元素運算式序列（以逗號分隔），並以括弧括住。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="9ff9f-215">例如， `(1, One)` 是 `(Int, Result)` 運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="9ff9f-216">除了常值以外，唯一的元組運算式是系結至元組值的符號、元組陣列的陣列元素，以及傳回元組的可呼叫調用。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="9ff9f-217">User-Defined 類型運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="9ff9f-218">使用者定義型別的常值包含型別名稱，後面接著型別的基底元組類型的元組常值。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="9ff9f-219">例如，如果 `IntPair` 是根據的使用者定義型別，則 `(Int, Int)` `IntPair(2, 3)` 是該類型的有效常值。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="9ff9f-220">除了常值以外，唯一的使用者定義型別運算式是系結至該類型值的符號、該類型陣列的陣列元素，以及傳回該類型的可呼叫調用。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="9ff9f-221">解除包裝運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-221">Unwrap Expressions</span></span>

<span data-ttu-id="9ff9f-222">在中，解除包裝 Q# 運算子是尾端驚嘆號 `!` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="9ff9f-223">例如，如果 `IntPair` 是具有基礎類型的使用者定義型別， `(Int, Int)` 而且 `s` 是具有值的變數，則 `IntPair(2, 3)` `s!` 為 `(2, 3)` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="9ff9f-224">針對其他使用者定義型別所定義的使用者定義型別，您可以重複解除包裝運算子。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="9ff9f-225">例如， `s!!` 表示的雙重解除包裝值 `s` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="9ff9f-226">因此，如果 `WrappedPair` 是具有基礎類型的使用者定義型別 `IntPair` ，而且 `t` 是具有值的變數 `WrappedPair(IntPair(1,2))` ，則 `t!!` 為 `(1,2)` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="9ff9f-227">運算子的優先順序高於除 `!` `[]` 陣列索引和切割以外的其他所有運算子。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="9ff9f-228">`!` 然後系結 `[]` positionally; 也就是說， `a[i]![3]` 會讀取為 `((a[i])!)[3]` ： take 的 `i` 第一個專案 `a` ，將它解除包裝，然後取得未包裝值的第三個元素 (必須是陣列) 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="9ff9f-229">運算子的優先順序 `!` 有一個可能不明顯的影響。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="9ff9f-230">如果函式或作業傳回的值接著會解除包裝，則函式或作業呼叫必須以括弧括住，讓引數元組系結至呼叫，而不是解除包裝。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="9ff9f-231">例如：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="9ff9f-232">陣列運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-232">Array Expressions</span></span>

<span data-ttu-id="9ff9f-233">陣列常值是以逗號分隔的一或多個元素運算式的序列，並以方括弧括住 `[]` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="9ff9f-234">所有元素都必須與相同的類型相容。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="9ff9f-235">假設有兩個相同類型的陣列，請使用二元 `+` 運算子來形成新的陣列，這是兩個數組的串連。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="9ff9f-236">例如：`[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="9ff9f-237">陣列建立</span><span class="sxs-lookup"><span data-stu-id="9ff9f-237">Array Creation</span></span>

<span data-ttu-id="9ff9f-238">假設有型別和 `Int` 運算式，請使用 `new` 運算子來配置指定大小的新陣列。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="9ff9f-239">例如，配置 `new Int[i + 1]` `Int` 具有元素的新陣列 `i + 1` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="9ff9f-240">不允許空的陣列常值（例如 `[]` ）。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="9ff9f-241">相反地，您可以使用建立長度為零的陣列 `new T[0]` ，其中 `T` 是適合的型別預留位置。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="9ff9f-242">新陣列的元素會初始化為類型相依的預設值。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="9ff9f-243">在大部分的情況下，這會是零的變化。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="9ff9f-244">對於實體參考的量子位和 callables，沒有合理的預設值。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="9ff9f-245">因此，對於這些型別，預設值是不正確參考，您無法使用而不會造成執行階段錯誤，類似于 c # 或 JAVA 等語言中的 null 參考。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="9ff9f-246">包含量子位或 callables 的陣列必須使用非預設值來初始化，才能安全地使用其專案。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="9ff9f-247">如需適當的初始化常式，請參閱 <xref:Microsoft.Quantum.Arrays> 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-247">For suitable initialization routines, see <xref:Microsoft.Quantum.Arrays>.</span></span>

<span data-ttu-id="9ff9f-248">每個類型的預設值為：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-248">The default values for each type are:</span></span>

<span data-ttu-id="9ff9f-249">類型</span><span class="sxs-lookup"><span data-stu-id="9ff9f-249">Type</span></span> | <span data-ttu-id="9ff9f-250">預設</span><span class="sxs-lookup"><span data-stu-id="9ff9f-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="9ff9f-251">_不正確量子位_</span><span class="sxs-lookup"><span data-stu-id="9ff9f-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="9ff9f-252">空白範圍， `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="9ff9f-253">_調用無效_</span><span class="sxs-lookup"><span data-stu-id="9ff9f-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="9ff9f-254">元組類型會依元素初始化元素。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="9ff9f-255">陣列元素</span><span class="sxs-lookup"><span data-stu-id="9ff9f-255">Array Elements</span></span>

<span data-ttu-id="9ff9f-256">指定陣列運算式和運算式之後 `Int` ，會使用陣列元素運算子來形成新的運算式 `[]` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="9ff9f-257">新運算式的類型與陣列的元素類型相同。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="9ff9f-258">例如，如果系結 `a` 至類型的陣列，則 `Double` `a[4]` 為 `Double` 運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="9ff9f-259">如果陣列運算式不是簡單的識別碼，您必須將它括在括弧中，以選取專案。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="9ff9f-260">例如，如果 `a` 和 `b` 都是類型的陣列 `Int` ，則串連的元素會以下列方式表示：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="9ff9f-261">中的所有陣列 Q# 都是以零為基底。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="9ff9f-262">亦即，陣列的第一個元素 `a` 一律為 `a[0]` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="9ff9f-263">陣列配量</span><span class="sxs-lookup"><span data-stu-id="9ff9f-263">Array Slices</span></span>

<span data-ttu-id="9ff9f-264">指定陣列運算式和運算式之後 `Range` ，會使用陣列配量運算子來形成新的運算式 `[ ]` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="9ff9f-265">新的運算式與陣列的類型相同，而且包含依的專案（依所定義的順序）編制索引的陣列專案 `Range` `Range` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="9ff9f-266">例如，如果系結 `a` 至類型的陣列，則 `Double` `a[3..-1..0]` 是 `Double[]` 包含前四個專案的運算式， `a` 但會依它們出現在中的相反順序 `a` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="9ff9f-267">如果 `Range` 是空的，則產生的陣列配量為零長度。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="9ff9f-268">就像參考陣列元素一樣，如果陣列運算式不是簡單的識別碼，您必須將它括在括弧中，以進行配量。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="9ff9f-269">例如，如果 `a` 和 `b` 都是類型的陣列 `Int` ，則串連的配量會以下列方式表示：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="9ff9f-270">推斷的開始/結束值</span><span class="sxs-lookup"><span data-stu-id="9ff9f-270">Inferred start/end values</span></span>

<span data-ttu-id="9ff9f-271">從 [0.8 版](xref:microsoft.quantum.relnotes)開始，我們支援範圍切割的內容運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="9ff9f-272">尤其是，您可以在範圍切割運算式的內容中省略範圍開始和結束值。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="9ff9f-273">在這種情況下，編譯器會套用下列規則，以推斷範圍的預期分隔符號：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="9ff9f-274">如果省略範圍 *開始* 值，則推斷開始值</span><span class="sxs-lookup"><span data-stu-id="9ff9f-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="9ff9f-275">如果未指定任何步驟，或指定的步驟是正數，則為零。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="9ff9f-276">如果指定的步驟為負數，則為配量陣列的長度減一。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="9ff9f-277">如果省略範圍 *結束* 值，則推斷結束值</span><span class="sxs-lookup"><span data-stu-id="9ff9f-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="9ff9f-278">如果未指定任何步驟，或指定的步驟是正數，則為配量陣列的長度減一。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="9ff9f-279">如果指定的步驟為負數，則為零。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="9ff9f-280">部份範例如下：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-280">Some examples are:</span></span>

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="9ff9f-281">複製和更新運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="9ff9f-282">由於所有 Q# 型別都是實值型別 (量子位採用有點特殊的角色) ，因此當值系結至符號或重新系結符號時，就會建立「複製」。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="9ff9f-283">也就是說，的行為與 Q# 使用指派運算子建立複本的行為相同。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="9ff9f-284">當然，在實務上，只會視需要重新建立相關的部分。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="9ff9f-285">這會影響您複製陣列的方式，因為不可能更新陣列專案。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="9ff9f-286">若要修改現有的陣列，需要利用 *複製和更新* 機制。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="9ff9f-287">您可以透過使用運算子和的 *複製和更新* 運算式，從現有的陣列建立新的陣列 `w/` `<-` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="9ff9f-288">複製和更新運算式是表單的運算式 `expression1 w/ expression2 <- expression3` ，其中</span><span class="sxs-lookup"><span data-stu-id="9ff9f-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="9ff9f-289">`expression1` 必須是類型 `T[]` 的類型 `T` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="9ff9f-290">`expression2` 定義中指定要修改之陣列中的哪些索引 `expression1` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="9ff9f-291">`expression2` 必須是類型 `Int` 或類型 `Range` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="9ff9f-292">`expression3` 這是 `expression1` 根據中指定的索引，用來更新中之專案)  (s 的值 `expression2` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="9ff9f-293">如果 `expression2` 是類型 `Int` ， `expression3` 必須為類型 `T` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="9ff9f-294">如果 `expression2` 是類型 `Range` ， `expression3` 必須為類型 `T[]` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="9ff9f-295">例如，複製和更新運算式 `arr w/ idx <- value` 會在中建立一個新的陣列，其中所有專案都會設定為中的對應元素 `arr` ，但 () 所指定的專案 `idx` ，其會設定為中) 的值 (`value` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="9ff9f-296">指定 `arr` 的包含陣列 `[0,1,2,3]` ，然後</span><span class="sxs-lookup"><span data-stu-id="9ff9f-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="9ff9f-297">`arr w/ 0 <- 10` 是陣列 `[10,1,2,3]` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="9ff9f-298">`arr w/ 2 <- 10` 是陣列 `[0,1,10,3]` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="9ff9f-299">`arr w/ 0..2..3 <- [10,12]` 是陣列 `[10,1,12,3]` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="9ff9f-300">已命名專案的複製和更新運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="9ff9f-301">使用者定義型別中的命名專案有類似的運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="9ff9f-302">例如，請考慮類型</span><span class="sxs-lookup"><span data-stu-id="9ff9f-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="9ff9f-303">如果 `c` 包含類型的值 `Complex(1., -1.)` ，則 `c w/ Re <- 0.` 為 `Complex` 評估為之類型的運算式 `Complex(0., -1.)` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="9ff9f-304">不規則陣列</span><span class="sxs-lookup"><span data-stu-id="9ff9f-304">Jagged Arrays</span></span>

<span data-ttu-id="9ff9f-305">不規則陣列（有時稱為「陣列陣列」）是其元素為數組的陣列。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="9ff9f-306">不規則陣列的元素可以是不同的大小。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="9ff9f-307">下列範例示範如何宣告和初始化表示乘法資料表的不規則陣列。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="9ff9f-308">Callables 的陣列</span><span class="sxs-lookup"><span data-stu-id="9ff9f-308">Arrays of callables</span></span> 

<span data-ttu-id="9ff9f-309">您也可以建立 callables 的陣列。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="9ff9f-310">如果通用元素類型是作業或函式類型，則所有專案都必須具有相同的輸入和輸出類型。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="9ff9f-311">陣列的元素類型支援所有元素所支援的任何 [函子](xref:microsoft.quantum.guide.operationsfunctions) 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="9ff9f-312">例如，如果 `Op1` 、 `Op2` 和都 `Op3` 是 `Qubit[] => Unit` 作業，但是 `Op1` 支援、，而且支援 `Adjoint` `Op2` `Controlled` `Op3` 兩者：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="9ff9f-313">`[Op1, Op2]` 是作業的陣列 `(Qubit[] => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="9ff9f-314">`[Op1, Op3]` 是作業的陣列 `(Qubit[] => Unit is Adj)` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="9ff9f-315">`[Op2, Op3]` 是作業的陣列 `(Qubit[] => Unit is Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="9ff9f-316">不過，雖然作業 `(Qubit[] => Unit is Adj)` 和  `(Qubit[] => Unit is Ctl)` 具有的通用基底類型 `(Qubit[] => Unit)` ，但這些作業的 *陣列* 不會共用通用基底類型。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="9ff9f-317">例如， `[[Op1], [Op2]]` 目前會引發錯誤，因為它會嘗試建立兩個不相容的陣列類型 `(Qubit[] => Unit is Adj)[]` 和中的陣列 `(Qubit[] => Unit is Ctl)[]` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="9ff9f-318">如需 callables 的詳細資訊，請參閱這個頁面上的可呼叫[運算式](#callable-expressions)或[中 Q# 的作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="9ff9f-319">條件運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-319">Conditional Expressions</span></span>

<span data-ttu-id="9ff9f-320">假設有兩個相同類型和布林運算式的運算式，則會使用問號、和分隔號來形成條件運算式 `?` `|` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="9ff9f-321">`a==b ? c | d`若為 true，則為條件運算式的值，如果為 false，則為 `c` `a==b` `d` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="9ff9f-322">使用 callables 的條件運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-322">Conditional expressions with callables</span></span>

<span data-ttu-id="9ff9f-323">條件運算式可能會評估為具有相同輸入和輸出但支援不同函子的作業。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="9ff9f-324">在此情況下，條件運算式的類型是具有輸入和輸出的作業，可支援這兩個運算式所支援的任何函子。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="9ff9f-325">例如，如果 `Op1` 、 `Op2` 和都 `Op3` 是 `Qubit[]=>Unit` ，但 `Op1` 支援 `Adjoint` `Op2` `Controlled` `Op3` 、和兩者都支援：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="9ff9f-326">`flag ? Op1 | Op2` 這是一項作業 `(Qubit[] => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="9ff9f-327">`flag ? Op1 | Op3` 這是一項作業 `(Qubit[] => Unit is Adj)` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="9ff9f-328">`flag ? Op2 | Op3` 這是一項作業 `(Qubit[] => Unit is Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="9ff9f-329">如果有兩個可能的結果運算式包括函數或作業呼叫，則只有在該結果是呼叫值的情況下，該呼叫才會發生。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="9ff9f-330">例如，在此情況下，如果是 true，則會叫用作業 `a==b ? C(qs) | D(qs)` `a==b` `C` ，如果是 false，則只會叫用作業 `D` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="9ff9f-331">這種方法類似于其他語言的 *簡短* 運算。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="9ff9f-332">可呼叫的運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-332">Callable Expressions</span></span>

<span data-ttu-id="9ff9f-333">可呼叫的常值是在編譯範圍中定義之作業或函式的名稱。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="9ff9f-334">例如， `X` 是參考標準程式庫作業的作業常值 `X` ，而且 `Message` 是參考標準程式庫函數的函式常值 `Message` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="9ff9f-335">如果作業支援 `Adjoint` 仿函數，則為作業 `Adjoint op` 運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="9ff9f-336">同樣地，如果作業支援 `Controlled` 仿函數，則 `Controlled op` 為作業運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="9ff9f-337">如需這些運算式類型的詳細資訊，請參閱 [呼叫](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)作業特製化。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="9ff9f-338">函子 (`Adjoint` 和 `Controlled`) 系結比其他所有運算子更緊密，除了解除包裝運算子 `!` 和的陣列索引之外 `[ ]` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="9ff9f-339">因此，下列各項都是有效的，前提是這些作業支援所使用的函子：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="9ff9f-340">類型參數化可呼叫運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="9ff9f-341">您可以使用可呼叫常值做為值，例如，將它指派給變數或將它傳遞給另一個可呼叫。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="9ff9f-342">在此情況下，如果可呼叫的具有 [類型參數](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)，您就必須提供參數作為可呼叫值的一部分。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="9ff9f-343">可呼叫的值不能有任何未指定的型別參數。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="9ff9f-344">例如，如果是具有簽章的函式 `Fun` `'T1->Unit` ：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="9ff9f-345">可呼叫調用運算式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="9ff9f-346">假設有一個可呼叫的運算式 (作業或函式) ，以及可呼叫的簽章之輸入類型的元組運算式，您可以藉由將元組運算式附加至可呼叫的運算式，來形成 *調用運算式* 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="9ff9f-347">調用運算式的類型是可呼叫之簽章的輸出類型。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="9ff9f-348">例如，如果是具有簽章的作業 `Op` `((Int, Qubit) => Double)` ， `Op(3, qubit1)` 則為類型的運算式 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="9ff9f-349">同樣地，如果是具有簽章的函 `Sin` `(Double -> Double)` `Sin(0.1)` 式，則為類型的運算式 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="9ff9f-350">最後，如果是具有簽章的函式 `Builder` `(Int -> (Int -> Int))` ，則 `Builder(3)` 是從 `Int` 到 `Int` 的函式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="9ff9f-351">叫用可呼叫值運算式的結果需要一組額外的括弧來括住可呼叫的運算式。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="9ff9f-352">因此，若要叫 `Builder` 用從上一個段落呼叫的結果，正確的語法為：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="9ff9f-353">叫用 [型別參數化](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) 可呼叫時，您可以在可呼叫的運算式之後，于角括弧內指定實際的型別參數 `< >` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="9ff9f-354">這通常不是必要動作，因為 Q# 編譯器會推斷實際的類型。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="9ff9f-355">但是，如果未指定型別參數化引數， [部分應用程式](xref:microsoft.quantum.guide.operationsfunctions#partial-application)*就* 需要它。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="9ff9f-356">將具有不同仿函數支援的作業傳遞給可呼叫的時，它也很有用。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="9ff9f-357">例如，如果有簽章，而且有簽章和簽章，則 `Func` `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` 會 `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` `Func` 使用 `Op1` 做為第一個引數做為第二個引數，並做為第三個引數 `Op2` `Op3` ：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="9ff9f-358">類型規格是必要的 `Op3` ，因為和 `Op1` 具有不同的類型，因此編譯器會將此視為不明確的，而不會有規格。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="9ff9f-359">運算子優先順序</span><span class="sxs-lookup"><span data-stu-id="9ff9f-359">Operator Precedence</span></span>

* <span data-ttu-id="9ff9f-360">除了之外，所有二元運算子都是右向關聯 `^` 。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="9ff9f-361">括弧，如果是 `[ ]` 陣列切割和索引，請在任何運算子之前系結。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="9ff9f-362">`Adjoint` `Controlled` 陣列索引之後，但在所有其他運算子之前的函子和系結。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="9ff9f-363">作業和函式呼叫的括弧也會在任何運算子之前系結，但在陣列索引和函子之後。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="9ff9f-364">Q# 依優先順序排列的運算子，從最高到最低：</span><span class="sxs-lookup"><span data-stu-id="9ff9f-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="9ff9f-365">運算子</span><span class="sxs-lookup"><span data-stu-id="9ff9f-365">Operator</span></span> | <span data-ttu-id="9ff9f-366">元</span><span class="sxs-lookup"><span data-stu-id="9ff9f-366">Arity</span></span> | <span data-ttu-id="9ff9f-367">描述</span><span class="sxs-lookup"><span data-stu-id="9ff9f-367">Description</span></span> | <span data-ttu-id="9ff9f-368">運算元類型</span><span class="sxs-lookup"><span data-stu-id="9ff9f-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="9ff9f-369">尾隨 `!`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-369">trailing `!`</span></span> | <span data-ttu-id="9ff9f-370">一元</span><span class="sxs-lookup"><span data-stu-id="9ff9f-370">Unary</span></span> | <span data-ttu-id="9ff9f-371">解除包裝</span><span class="sxs-lookup"><span data-stu-id="9ff9f-371">Unwrap</span></span> | <span data-ttu-id="9ff9f-372">任何使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="9ff9f-372">Any user-defined type</span></span>
 <span data-ttu-id="9ff9f-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="9ff9f-374">一元</span><span class="sxs-lookup"><span data-stu-id="9ff9f-374">Unary</span></span> | <span data-ttu-id="9ff9f-375">數值負、位補數、邏輯否定</span><span class="sxs-lookup"><span data-stu-id="9ff9f-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="9ff9f-376">`Int`、 `BigInt` 或適用于 `Double` `-` `Int` `BigInt` `~~~` `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="9ff9f-377">Binary</span><span class="sxs-lookup"><span data-stu-id="9ff9f-377">Binary</span></span> | <span data-ttu-id="9ff9f-378">整數乘冪</span><span class="sxs-lookup"><span data-stu-id="9ff9f-378">Integer power</span></span> | <span data-ttu-id="9ff9f-379">`Int`或 `BigInt` 作為指數的基底 `Int`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="9ff9f-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="9ff9f-381">Binary</span><span class="sxs-lookup"><span data-stu-id="9ff9f-381">Binary</span></span> | <span data-ttu-id="9ff9f-382">除法、乘法、整數模數</span><span class="sxs-lookup"><span data-stu-id="9ff9f-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="9ff9f-383">`Int`、 `BigInt` `Double` 適用于 `/` 和 `*` 的 `Int` 、 `BigInt` 或 `%`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="9ff9f-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-384">`+`, `-`</span></span> | <span data-ttu-id="9ff9f-385">Binary</span><span class="sxs-lookup"><span data-stu-id="9ff9f-385">Binary</span></span> | <span data-ttu-id="9ff9f-386">加法或字串和陣列串連，減法</span><span class="sxs-lookup"><span data-stu-id="9ff9f-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="9ff9f-387">`Int`、 `BigInt` 或 `Double` 、或 `String` 的任何陣列類型 `+`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="9ff9f-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="9ff9f-389">Binary</span><span class="sxs-lookup"><span data-stu-id="9ff9f-389">Binary</span></span> | <span data-ttu-id="9ff9f-390">左移、右移右移</span><span class="sxs-lookup"><span data-stu-id="9ff9f-390">Left shift, right shift</span></span> | <span data-ttu-id="9ff9f-391">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="9ff9f-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="9ff9f-393">Binary</span><span class="sxs-lookup"><span data-stu-id="9ff9f-393">Binary</span></span> | <span data-ttu-id="9ff9f-394">小於、小於或等於、大於、大於或等於比較的比較結果</span><span class="sxs-lookup"><span data-stu-id="9ff9f-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="9ff9f-395">`Int`、`BigInt` 或 `Double`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="9ff9f-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-396">`==`, `!=`</span></span> | <span data-ttu-id="9ff9f-397">Binary</span><span class="sxs-lookup"><span data-stu-id="9ff9f-397">Binary</span></span> | <span data-ttu-id="9ff9f-398">相等、不等於比較</span><span class="sxs-lookup"><span data-stu-id="9ff9f-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="9ff9f-399">任何基本類型</span><span class="sxs-lookup"><span data-stu-id="9ff9f-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="9ff9f-400">Binary</span><span class="sxs-lookup"><span data-stu-id="9ff9f-400">Binary</span></span> | <span data-ttu-id="9ff9f-401">位元 AND</span><span class="sxs-lookup"><span data-stu-id="9ff9f-401">Bitwise AND</span></span> | <span data-ttu-id="9ff9f-402">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="9ff9f-403">Binary</span><span class="sxs-lookup"><span data-stu-id="9ff9f-403">Binary</span></span> | <span data-ttu-id="9ff9f-404">位元 XOR</span><span class="sxs-lookup"><span data-stu-id="9ff9f-404">Bitwise XOR</span></span> | <span data-ttu-id="9ff9f-405">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="9ff9f-406">Binary</span><span class="sxs-lookup"><span data-stu-id="9ff9f-406">Binary</span></span> | <span data-ttu-id="9ff9f-407">位元 OR</span><span class="sxs-lookup"><span data-stu-id="9ff9f-407">Bitwise OR</span></span> | <span data-ttu-id="9ff9f-408">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="9ff9f-409">Binary</span><span class="sxs-lookup"><span data-stu-id="9ff9f-409">Binary</span></span> | <span data-ttu-id="9ff9f-410">邏輯 AND</span><span class="sxs-lookup"><span data-stu-id="9ff9f-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="9ff9f-411">Binary</span><span class="sxs-lookup"><span data-stu-id="9ff9f-411">Binary</span></span> | <span data-ttu-id="9ff9f-412">邏輯 OR</span><span class="sxs-lookup"><span data-stu-id="9ff9f-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="9ff9f-413">Binary/三元</span><span class="sxs-lookup"><span data-stu-id="9ff9f-413">Binary/Ternary</span></span> | <span data-ttu-id="9ff9f-414">範圍運算子</span><span class="sxs-lookup"><span data-stu-id="9ff9f-414">Range operator</span></span> | `Int`
 <span data-ttu-id="9ff9f-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-415">`?` `|`</span></span> | <span data-ttu-id="9ff9f-416">三元</span><span class="sxs-lookup"><span data-stu-id="9ff9f-416">Ternary</span></span> | <span data-ttu-id="9ff9f-417">條件式</span><span class="sxs-lookup"><span data-stu-id="9ff9f-417">Conditional</span></span> | <span data-ttu-id="9ff9f-418">`Bool` 針對左手邊</span><span class="sxs-lookup"><span data-stu-id="9ff9f-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="9ff9f-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="9ff9f-419">`w/` `<-`</span></span> | <span data-ttu-id="9ff9f-420">三元</span><span class="sxs-lookup"><span data-stu-id="9ff9f-420">Ternary</span></span> | <span data-ttu-id="9ff9f-421">複製和更新</span><span class="sxs-lookup"><span data-stu-id="9ff9f-421">Copy-and-update</span></span> | <span data-ttu-id="9ff9f-422">請參閱 [複製和更新運算式](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="9ff9f-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="9ff9f-423">後續步驟</span><span class="sxs-lookup"><span data-stu-id="9ff9f-423">Next steps</span></span>

<span data-ttu-id="9ff9f-424">現在您可以使用中的運算式 Q# ，請移至[中的 Q# 作業和](xref:microsoft.quantum.guide.operationsfunctions)函式，以瞭解如何定義和呼叫作業和函數。</span><span class="sxs-lookup"><span data-stu-id="9ff9f-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
