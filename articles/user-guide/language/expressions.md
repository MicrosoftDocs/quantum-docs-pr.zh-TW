---
title: 中的運算式Q#
description: 瞭解如何指定、參考和合併常數、變數、運算子、作業和函式，做為中的運算式 Q# 。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: b6cc97dfee05dc843e213e84f17043714a8a9656
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869608"
---
# <a name="expressions-in-no-locq"></a><span data-ttu-id="1bf26-103">中的運算式Q#</span><span class="sxs-lookup"><span data-stu-id="1bf26-103">Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="1bf26-104">數值運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-104">Numeric Expressions</span></span>

<span data-ttu-id="1bf26-105">數值運算式是、或類型的運算式 `Int` `BigInt` `Double` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="1bf26-106">也就是說，它們可以是整數或浮點數。</span><span class="sxs-lookup"><span data-stu-id="1bf26-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="1bf26-107">`Int`中的常值 Q# 會寫入為一連串的數位。</span><span class="sxs-lookup"><span data-stu-id="1bf26-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="1bf26-108">以和前置詞分別支援和寫入十六進位和二進位整數 `0x` `0b` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="1bf26-109">`BigInt`中的常值 Q# 具有尾端 `l` 或 `L` 尾碼。</span><span class="sxs-lookup"><span data-stu-id="1bf26-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="1bf26-110">支援十六進位大整數，並以 "0x" 前置詞寫入。</span><span class="sxs-lookup"><span data-stu-id="1bf26-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="1bf26-111">因此，下列是常值的所有有效用法 `BigInt` ：</span><span class="sxs-lookup"><span data-stu-id="1bf26-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="1bf26-112">`Double`中的常 Q# 值是使用十進位數撰寫的浮點數。</span><span class="sxs-lookup"><span data-stu-id="1bf26-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="1bf26-113">它們可以使用或不含小數點、 `.` 或以 ' e ' 或 ' e ' 表示的指數部分來撰寫， (之後只有可能的負號和十進位數是有效的) 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="1bf26-114">下列是有效的 `Double` 常值： `0.0` 、 `1.2e5` 、 `1e-5` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="1bf26-115">假設有任何元素類型的陣列運算式，您可以使用內 `Int` 建函數來形成運算式 [`Length`](xref:microsoft.quantum.core.length) ，並以括弧括住陣列運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="1bf26-116">例如，如果系結 `a` 至陣列，則 `Length(a)` 為整數運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="1bf26-117">如果 `b` 是整數陣列的陣列， `Int[][]` 則 `Length(b)` 是中的子陣列數目 `b` ，而 `Length(b[1])` 是中第二個子陣列中的整數數目 `b` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="1bf26-118">假設有兩個相同類型的數值運算式，則 `+` 可以使用二元運算子、、 `-` `*` 和 `/` 來形成新的數值運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="1bf26-119">新運算式的類型與組成運算式的類型相同。</span><span class="sxs-lookup"><span data-stu-id="1bf26-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="1bf26-120">假設有兩個整數運算式，請使用二元運算子 `^` (power) 以形成新的整數運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="1bf26-121">同樣地，您也可以使用搭配 `^` 兩個雙重運算式來形成新的 double 運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="1bf26-122">最後，您可以使用 `^` 左邊的大整數和右邊的整數來形成新的大整數運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="1bf26-123">在此情況下，第二個參數必須符合32位;如果不是，就會引發執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="1bf26-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="1bf26-124">假設有兩個整數或大整數運算式，請使用 `%` (模數) ， `&&&` (位 and) 、 `|||` (位 or) 或 `^^^` (位 XOR) 運算子，形成新的整數或大整數運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="1bf26-125">指定左邊的整數或大整數運算式，以及右邊的整數運算式時，請使用 `<<<` (算術左移位) 或 `>>>` (算術向右移位) 運算子，以建立與左邊運算式相同類型的新運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="1bf26-126">第二個參數 (移位量) 為移位運算的位移必須大於或等於零;負位移金額的行為未定義。</span><span class="sxs-lookup"><span data-stu-id="1bf26-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="1bf26-127">任何移位作業的移位量也必須符合32位;如果不是，就會引發執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="1bf26-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="1bf26-128">如果移位的數位是整數，則會解讀位移量 `mod 64` ; 也就是說，1和位移65的位移會有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="1bf26-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="1bf26-129">對於整數和大整數值，移位是算術。</span><span class="sxs-lookup"><span data-stu-id="1bf26-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="1bf26-130">將負數值向左或向右移位會產生負數。</span><span class="sxs-lookup"><span data-stu-id="1bf26-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="1bf26-131">也就是說，將一個步驟向左或向右移位，會分別與乘法或除以2相同。</span><span class="sxs-lookup"><span data-stu-id="1bf26-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="1bf26-132">整數除法和整數模數會遵循與 c # 相同的負數行為。</span><span class="sxs-lookup"><span data-stu-id="1bf26-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="1bf26-133">也就是， `a % b` 一律具有相同的正負號 `a` ，而且 `b * (a / b) + a % b` 一律等於 `a` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span>
<span data-ttu-id="1bf26-134">例如：</span><span class="sxs-lookup"><span data-stu-id="1bf26-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="1bf26-135">5</span><span class="sxs-lookup"><span data-stu-id="1bf26-135">5</span></span> | <span data-ttu-id="1bf26-136">2</span><span class="sxs-lookup"><span data-stu-id="1bf26-136">2</span></span> | <span data-ttu-id="1bf26-137">2</span><span class="sxs-lookup"><span data-stu-id="1bf26-137">2</span></span> | <span data-ttu-id="1bf26-138">1</span><span class="sxs-lookup"><span data-stu-id="1bf26-138">1</span></span>
 <span data-ttu-id="1bf26-139">5</span><span class="sxs-lookup"><span data-stu-id="1bf26-139">5</span></span> | <span data-ttu-id="1bf26-140">-2</span><span class="sxs-lookup"><span data-stu-id="1bf26-140">-2</span></span> | <span data-ttu-id="1bf26-141">-2</span><span class="sxs-lookup"><span data-stu-id="1bf26-141">-2</span></span> | <span data-ttu-id="1bf26-142">1</span><span class="sxs-lookup"><span data-stu-id="1bf26-142">1</span></span>
 <span data-ttu-id="1bf26-143">-5</span><span class="sxs-lookup"><span data-stu-id="1bf26-143">-5</span></span> | <span data-ttu-id="1bf26-144">2</span><span class="sxs-lookup"><span data-stu-id="1bf26-144">2</span></span> | <span data-ttu-id="1bf26-145">-2</span><span class="sxs-lookup"><span data-stu-id="1bf26-145">-2</span></span> | <span data-ttu-id="1bf26-146">-1</span><span class="sxs-lookup"><span data-stu-id="1bf26-146">-1</span></span>
 <span data-ttu-id="1bf26-147">-5</span><span class="sxs-lookup"><span data-stu-id="1bf26-147">-5</span></span> | <span data-ttu-id="1bf26-148">-2</span><span class="sxs-lookup"><span data-stu-id="1bf26-148">-2</span></span> | <span data-ttu-id="1bf26-149">2</span><span class="sxs-lookup"><span data-stu-id="1bf26-149">2</span></span> | <span data-ttu-id="1bf26-150">-1</span><span class="sxs-lookup"><span data-stu-id="1bf26-150">-1</span></span>

<span data-ttu-id="1bf26-151">大整數除法和模數運算的運作方式相同。</span><span class="sxs-lookup"><span data-stu-id="1bf26-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="1bf26-152">假設有任何數值運算式，您可以使用一元運算子來形成新的運算式 `-` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="1bf26-153">新的運算式與組成運算式的類型相同。</span><span class="sxs-lookup"><span data-stu-id="1bf26-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="1bf26-154">假設有任何整數或大整數運算式，您可以使用 `~~~` (位補數) 一元運算子來形成相同類型的新運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="1bf26-155">布林運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-155">Boolean Expressions</span></span>

<span data-ttu-id="1bf26-156">這兩個 `Bool` 常值為 `true` 和 `false` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="1bf26-157">假設有兩個相同基本類型的運算式，則 `==` 和 `!=` 二元運算子可用來建立 `Bool` 運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="1bf26-158">如果兩個運算式相等，則運算式為 true，否則為 false。</span><span class="sxs-lookup"><span data-stu-id="1bf26-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="1bf26-159">可能不會比較使用者定義類型的值，只可以比較其未包裝的值。</span><span class="sxs-lookup"><span data-stu-id="1bf26-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="1bf26-160">例如，使用「解除包裝」運算子 `!` () 中的[類型 Q# ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)詳細說明。</span><span class="sxs-lookup"><span data-stu-id="1bf26-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="1bf26-161">值的相等比較 `Qubit` 是識別相等的，也就是兩個運算式是否識別相同的 qubit。</span><span class="sxs-lookup"><span data-stu-id="1bf26-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="1bf26-162">這兩個 qubits 的狀態不會由這項比較進行比較、存取、測量或修改。</span><span class="sxs-lookup"><span data-stu-id="1bf26-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="1bf26-163">值的相等比較 `Double` 可能會因為進位效果而誤導。</span><span class="sxs-lookup"><span data-stu-id="1bf26-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="1bf26-164">例如： `49.0 * (1.0/49.0) != 1.0` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="1bf26-165">假設有兩個數值運算式， `>` `<` `>=` `<=` 如果第一個運算式分別大於、小於、大於或等於或小於或等於第二個運算式，則二元運算子、、和可能會用來建立新的布林值運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="1bf26-166">假設有兩個布林運算式，請使用 `and` 二元運算子來建立新的布林運算式，如果兩個運算式都是 true，則為 true。</span><span class="sxs-lookup"><span data-stu-id="1bf26-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="1bf26-167">同樣地， `or` 如果兩個運算式的其中一個為 true，則使用運算子會建立 true 的運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="1bf26-168">假設有任何布林運算式， `not` 一元運算子可用來建立新的布林運算式，如果組成運算式為 false，則為 true。</span><span class="sxs-lookup"><span data-stu-id="1bf26-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="1bf26-169">字串運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-169">String expressions</span></span>

<span data-ttu-id="1bf26-170">Q#允許在語句中使用字串， `fail` (在[控制流程](xref:microsoft.quantum.guide.controlflow#fail-statement)) 和標準函式中說明 [`Message`](xref:microsoft.quantum.intrinsic.message) 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span> <span data-ttu-id="1bf26-171">後者的特定行為取決於所使用的模擬器，但通常會在程式中呼叫時，將訊息寫入主機主控台 Q# 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="1bf26-172">中的字串 Q# 可以是常值或字串插值。</span><span class="sxs-lookup"><span data-stu-id="1bf26-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="1bf26-173">字串常值類似于大部分語言中的簡單字串常值：以雙引號括住的 Unicode 字元序列 `" "` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="1bf26-174">在字串內，使用反斜線字元 `\` 來將雙引號字元 (`\"`) ，或插入新的 ( `\n` ) 、回車 () 或索引標籤 `\r` (`\t`) 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="1bf26-175">例如：</span><span class="sxs-lookup"><span data-stu-id="1bf26-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="1bf26-176">插入字串</span><span class="sxs-lookup"><span data-stu-id="1bf26-176">Interpolated strings</span></span>

<span data-ttu-id="1bf26-177">Q#String 插補的語法是 c # 語法的子集。</span><span class="sxs-lookup"><span data-stu-id="1bf26-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="1bf26-178">以下是相關的重點 Q# ：</span><span class="sxs-lookup"><span data-stu-id="1bf26-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="1bf26-179">若要將字串常值識別為插入字串，請在其前面加上 `$` 符號。</span><span class="sxs-lookup"><span data-stu-id="1bf26-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="1bf26-180">`$`開始字串常值的和之間不能有空白字元 `"` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="1bf26-181">以下是使用函式 [`Message`](xref:microsoft.quantum.intrinsic.message) 將測量結果與其他運算式一起寫入主控台的基本範例 Q# 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-181">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="1bf26-182">任何有效 Q# 的運算式可能會出現在字串插值中。</span><span class="sxs-lookup"><span data-stu-id="1bf26-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="1bf26-183">插補字串內的運算式 Q# 會遵循語法，而不是 c # 語法。</span><span class="sxs-lookup"><span data-stu-id="1bf26-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="1bf26-184">最明顯的差異在於不 Q# 支援逐字 (多行) 插入字串。</span><span class="sxs-lookup"><span data-stu-id="1bf26-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="1bf26-185">如需 c # 語法的詳細資訊，請參閱[*字串插值*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。</span><span class="sxs-lookup"><span data-stu-id="1bf26-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="1bf26-186">範圍運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-186">Range Expressions</span></span>

<span data-ttu-id="1bf26-187">假設有任何三個 `Int` 運算式 `start` 、 `step` 和 `stop` ，則運算式 `start .. step .. stop` 為範圍運算式，其第一個元素為 `start` 、第二個元素為 `start+step` 、第三個元素為 `start+step+step` ，依此類推，直到您通過為止 `stop` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="1bf26-188">例如，如果是正數和，範圍可能會是空的 `step` `stop < start` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="1bf26-189">範圍包含在兩端。</span><span class="sxs-lookup"><span data-stu-id="1bf26-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="1bf26-190">也就是說，如果和之間的差異 `start` `stop` 是的整數倍數 `step` ，則範圍的最後一個元素會是 `stop` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="1bf26-191">假設有兩個 `Int` 運算式 `start` 和 `stop` ，運算式 `start .. stop` 就是等於的範圍運算式 `start .. 1 .. stop` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="1bf26-192">請注意， `step` 即使小於，隱含也是 + 1 `stop` `start` ; 在這種情況下，範圍是空的。</span><span class="sxs-lookup"><span data-stu-id="1bf26-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="1bf26-193">一些範例範圍如下：</span><span class="sxs-lookup"><span data-stu-id="1bf26-193">Some example ranges are:</span></span>

- <span data-ttu-id="1bf26-194">`1..3`為1、2、3的範圍。</span><span class="sxs-lookup"><span data-stu-id="1bf26-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="1bf26-195">`2..2..5`是範圍2，4。</span><span class="sxs-lookup"><span data-stu-id="1bf26-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="1bf26-196">`2..2..6`為範圍2、4、6。</span><span class="sxs-lookup"><span data-stu-id="1bf26-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="1bf26-197">`6..-2..2`為6、4、2的範圍。</span><span class="sxs-lookup"><span data-stu-id="1bf26-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="1bf26-198">`2..1`這是空的範圍。</span><span class="sxs-lookup"><span data-stu-id="1bf26-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="1bf26-199">`2..6..7`為範圍2。</span><span class="sxs-lookup"><span data-stu-id="1bf26-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="1bf26-200">`2..2..1`這是空的範圍。</span><span class="sxs-lookup"><span data-stu-id="1bf26-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="1bf26-201">`1..-1..2`這是空的範圍。</span><span class="sxs-lookup"><span data-stu-id="1bf26-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="1bf26-202">Qubit 運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-202">Qubit Expressions</span></span>

<span data-ttu-id="1bf26-203">唯一的 `Qubit` 運算式是系結至 `Qubit` 陣列的值或陣列元素的符號 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="1bf26-204">沒有任何 `Qubit` 常值。</span><span class="sxs-lookup"><span data-stu-id="1bf26-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="1bf26-205">Pauli 運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-205">Pauli Expressions</span></span>

<span data-ttu-id="1bf26-206">、、和這四個 `Pauli` 值 `PauliI` `PauliX` `PauliY` `PauliZ` 都是有效的 `Pauli` 運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="1bf26-207">除了這以外，唯一的 `Pauli` 運算式是系結至 `Pauli` 陣列值或陣列元素的符號 `Pauli` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="1bf26-208">結果運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-208">Result Expressions</span></span>

<span data-ttu-id="1bf26-209">和這兩個 `Result` 值 `One` `Zero` 都是有效的 `Result` 運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="1bf26-210">除了這以外，唯一的 `Result` 運算式是系結至 `Result` 陣列值或陣列元素的符號 `Result` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="1bf26-211">特別要注意的是，與 `One` 整數不相同 `1` ，而且它們之間沒有直接的轉換。</span><span class="sxs-lookup"><span data-stu-id="1bf26-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="1bf26-212">和的情況也是 `Zero` 如此 `0` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="1bf26-213">元組運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-213">Tuple Expressions</span></span>

<span data-ttu-id="1bf26-214">元組常值是適當類型的元素運算式序列，並以逗號分隔，並以括弧括住。</span><span class="sxs-lookup"><span data-stu-id="1bf26-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="1bf26-215">例如， `(1, One)` 是 `(Int, Result)` 運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="1bf26-216">除了常值以外，唯一的元組運算式是系結至元組值的符號、元組陣列的陣列元素，以及傳回元組的可呼叫調用。</span><span class="sxs-lookup"><span data-stu-id="1bf26-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="1bf26-217">使用者定義型別運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="1bf26-218">使用者自訂類型的常值是由類型名稱後面接著類型的基礎元組類型的元組常值所組成。</span><span class="sxs-lookup"><span data-stu-id="1bf26-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="1bf26-219">例如，如果 `IntPair` 是以為基礎的使用者定義型別 `(Int, Int)` ，則 `IntPair(2, 3)` 是該型別的有效常值。</span><span class="sxs-lookup"><span data-stu-id="1bf26-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="1bf26-220">除了常值以外，使用者定義型別的唯一運算式是系結至該型別、該型別陣列的陣列元素，以及傳回該型別之可呼叫調用的符號。</span><span class="sxs-lookup"><span data-stu-id="1bf26-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="1bf26-221">解除包裝運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-221">Unwrap Expressions</span></span>

<span data-ttu-id="1bf26-222">在中，解除包裝 Q# 運算子是尾端驚嘆號 `!` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="1bf26-223">例如，如果 `IntPair` 是具有基礎類型的使用者定義型別， `(Int, Int)` 而且是值為的 `s` 變數，則 `IntPair(2, 3)` `s!` 為 `(2, 3)` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="1bf26-224">針對其他使用者定義類型所定義的使用者定義型別，您可以重複解除包裝運算子。</span><span class="sxs-lookup"><span data-stu-id="1bf26-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="1bf26-225">例如， `s!!` 表示的雙重解除包裝值 `s` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="1bf26-226">因此，如果 `WrappedPair` 是具有基礎類型的使用者定義型別 `IntPair` ，而 `t` 是具有值的變數 `WrappedPair(IntPair(1,2))` ，則 `t!!` 為 `(1,2)` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="1bf26-227">除了 `!` 陣列索引和切割以外，運算子的優先順序高於其他所有運算子 `[]` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="1bf26-228">`!`和系結 `[]` positionally; 也就是 `a[i]![3]` 讀取為 `((a[i])!)[3]` ：取得的 `i` 第個元素 `a` ，將它解除包裝，然後取得未包裝值的第3個元素， (必須是陣列) 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="1bf26-229">運算子的優先順序 `!` 有一個可能不明顯的影響。</span><span class="sxs-lookup"><span data-stu-id="1bf26-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="1bf26-230">如果函式或作業傳回值，因而解除包裝，則函式或作業呼叫必須以括弧括住，讓引數元組系結至呼叫，而不是系結。</span><span class="sxs-lookup"><span data-stu-id="1bf26-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="1bf26-231">例如：</span><span class="sxs-lookup"><span data-stu-id="1bf26-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="1bf26-232">陣列運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-232">Array Expressions</span></span>

<span data-ttu-id="1bf26-233">陣列常值是一系列的一或多個元素運算式，並以逗號分隔，並以方括弧括住 `[]` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="1bf26-234">所有元素都必須與相同的型別相容。</span><span class="sxs-lookup"><span data-stu-id="1bf26-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="1bf26-235">假設有兩個相同類型的陣列，請使用二元 `+` 運算子來形成新陣列，這是兩個數組的串連。</span><span class="sxs-lookup"><span data-stu-id="1bf26-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="1bf26-236">例如：`[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`。</span><span class="sxs-lookup"><span data-stu-id="1bf26-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="1bf26-237">陣列建立</span><span class="sxs-lookup"><span data-stu-id="1bf26-237">Array Creation</span></span>

<span data-ttu-id="1bf26-238">假設有類型和 `Int` 運算式，請使用 `new` 運算子來配置指定大小的新陣列。</span><span class="sxs-lookup"><span data-stu-id="1bf26-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="1bf26-239">例如，會配置 `new Int[i + 1]` `Int` 具有元素的新陣列 `i + 1` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="1bf26-240">不允許空的陣列常值（例如 `[]` ）。</span><span class="sxs-lookup"><span data-stu-id="1bf26-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="1bf26-241">相反地，您可以使用來建立長度為零的陣列 `new T[0]` ，其中 `T` 是適合類型的預留位置。</span><span class="sxs-lookup"><span data-stu-id="1bf26-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="1bf26-242">新陣列的元素會初始化為與類型相關的預設值。</span><span class="sxs-lookup"><span data-stu-id="1bf26-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="1bf26-243">在大部分的情況下，這會是零的部分變化。</span><span class="sxs-lookup"><span data-stu-id="1bf26-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="1bf26-244">對於實體參考的 qubits 和 callables 而言，沒有合理的預設值。</span><span class="sxs-lookup"><span data-stu-id="1bf26-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="1bf26-245">因此，在這些類型中，預設值是不會造成執行階段錯誤而無法使用的無效參考，類似于 c # 或 JAVA 等語言中的 null 參考。</span><span class="sxs-lookup"><span data-stu-id="1bf26-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="1bf26-246">包含 qubits 或 callables 的陣列必須使用非預設值進行初始化，才能安全地使用它們的元素。</span><span class="sxs-lookup"><span data-stu-id="1bf26-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="1bf26-247">如需適當的初始化常式，請參閱 <xref:microsoft.quantum.arrays> 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-247">For suitable initialization routines, see <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="1bf26-248">每種類型的預設值為：</span><span class="sxs-lookup"><span data-stu-id="1bf26-248">The default values for each type are:</span></span>

<span data-ttu-id="1bf26-249">類型</span><span class="sxs-lookup"><span data-stu-id="1bf26-249">Type</span></span> | <span data-ttu-id="1bf26-250">預設</span><span class="sxs-lookup"><span data-stu-id="1bf26-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="1bf26-251">_不正確 qubit_</span><span class="sxs-lookup"><span data-stu-id="1bf26-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="1bf26-252">空白範圍，`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="1bf26-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="1bf26-253">_可呼叫無效_</span><span class="sxs-lookup"><span data-stu-id="1bf26-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="1bf26-254">元組類型會依元素初始化元素。</span><span class="sxs-lookup"><span data-stu-id="1bf26-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="1bf26-255">陣列元素</span><span class="sxs-lookup"><span data-stu-id="1bf26-255">Array Elements</span></span>

<span data-ttu-id="1bf26-256">假設有陣列運算式和 `Int` 運算式，請使用陣列元素運算子來形成新的運算式 `[]` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="1bf26-257">新運算式的類型與陣列的元素類型相同。</span><span class="sxs-lookup"><span data-stu-id="1bf26-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="1bf26-258">例如，如果系結 `a` 至類型的陣列，則 `Double` `a[4]` 為 `Double` 運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="1bf26-259">如果陣列運算式不是簡單的識別碼，您必須將它括在括弧中，以選取元素。</span><span class="sxs-lookup"><span data-stu-id="1bf26-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="1bf26-260">例如，如果 `a` 和 `b` 都是類型的陣列 `Int` ，則串連中的元素會表示為：</span><span class="sxs-lookup"><span data-stu-id="1bf26-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="1bf26-261">中的所有陣列 Q# 都是以零為基底。</span><span class="sxs-lookup"><span data-stu-id="1bf26-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="1bf26-262">也就是說，陣列的第一個元素 `a` 一定是 `a[0]` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="1bf26-263">陣列配量</span><span class="sxs-lookup"><span data-stu-id="1bf26-263">Array Slices</span></span>

<span data-ttu-id="1bf26-264">假設有陣列運算式和 `Range` 運算式，請使用陣列配量運算子來形成新的運算式 `[ ]` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="1bf26-265">新的運算式與陣列具有相同的類型，並且包含以的專案編制索引的陣列專案（依照所 `Range` 定義的順序） `Range` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="1bf26-266">例如，如果系結 `a` 至類型的陣列，則 `Double` `a[3..-1..0]` 是 `Double[]` 包含前四個專案的運算式， `a` 但在中出現的順序則是相反的 `a` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="1bf26-267">如果 `Range` 是空的，則產生的陣列配量為零長度。</span><span class="sxs-lookup"><span data-stu-id="1bf26-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="1bf26-268">就像參考陣列專案一樣，如果陣列運算式不是簡單的識別碼，您必須將它括在括弧中以進行配量。</span><span class="sxs-lookup"><span data-stu-id="1bf26-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="1bf26-269">例如，如果 `a` 和 `b` 都是類型的陣列 `Int` ，則串連中的配量會表示為：</span><span class="sxs-lookup"><span data-stu-id="1bf26-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="1bf26-270">推斷的開始/結束值</span><span class="sxs-lookup"><span data-stu-id="1bf26-270">Inferred start/end values</span></span>

<span data-ttu-id="1bf26-271">從[0.8 版](xref:microsoft.quantum.relnotes)開始，我們支援範圍切割的內容相關運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="1bf26-272">特別是，您可能會在範圍切割運算式的內容中省略範圍開始和結束值。</span><span class="sxs-lookup"><span data-stu-id="1bf26-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="1bf26-273">在這種情況下，編譯器會套用下列規則，以推斷範圍的預期分隔符號：</span><span class="sxs-lookup"><span data-stu-id="1bf26-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="1bf26-274">如果省略範圍*起始*值，則推斷的起始值</span><span class="sxs-lookup"><span data-stu-id="1bf26-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="1bf26-275">如果未指定任何步驟，或指定的步驟是正數，則為零。</span><span class="sxs-lookup"><span data-stu-id="1bf26-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="1bf26-276">如果指定的步驟是負數，則為已切割陣列的長度減一。</span><span class="sxs-lookup"><span data-stu-id="1bf26-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="1bf26-277">如果省略範圍*結束*值，則推斷的結束值</span><span class="sxs-lookup"><span data-stu-id="1bf26-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="1bf26-278">如果未指定任何步驟，或指定的步驟是正數，則為已切割陣列的長度減一。</span><span class="sxs-lookup"><span data-stu-id="1bf26-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="1bf26-279">如果指定的步驟是負數，則為零。</span><span class="sxs-lookup"><span data-stu-id="1bf26-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="1bf26-280">部份範例如下：</span><span class="sxs-lookup"><span data-stu-id="1bf26-280">Some examples are:</span></span>

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="1bf26-281">複製和更新運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="1bf26-282">由於所有 Q# 類型都是 (的實值型別，而 qubits 採用有點特殊的角色) ，因此，當值系結至符號或符號重新系結時，就會建立「複製」。</span><span class="sxs-lookup"><span data-stu-id="1bf26-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="1bf26-283">也就是說，的行為與 Q# 使用指派運算子建立複本時相同。</span><span class="sxs-lookup"><span data-stu-id="1bf26-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="1bf26-284">當然，在實務上，只有相關的部分會在需要時重新建立。</span><span class="sxs-lookup"><span data-stu-id="1bf26-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="1bf26-285">這會影響您複製陣列的方式，因為不可能更新陣列專案。</span><span class="sxs-lookup"><span data-stu-id="1bf26-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="1bf26-286">若要修改現有的陣列，您必須利用*複製和更新*機制。</span><span class="sxs-lookup"><span data-stu-id="1bf26-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="1bf26-287">您可以透過使用運算子和的「*複製並更新*」運算式，從現有的陣列建立新的陣列 `w/` `<-` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="1bf26-288">複製和更新運算式是格式的運算式 `expression1 w/ expression2 <- expression3` ，其中</span><span class="sxs-lookup"><span data-stu-id="1bf26-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="1bf26-289">`expression1`必須是 `T[]` 某種類型的類型 `T` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="1bf26-290">`expression2`定義在中指定要修改之陣列中的哪些索引 `expression1` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="1bf26-291">`expression2`必須是類型 `Int` 或類型 `Range` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="1bf26-292">`expression3`這是 `expression1` 根據中指定的索引，用來更新中專案的 (s) 值 `expression2` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="1bf26-293">如果 `expression2` 是類型 `Int` ， `expression3` 必須是類型 `T` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="1bf26-294">如果 `expression2` 是類型 `Range` ， `expression3` 必須是類型 `T[]` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="1bf26-295">例如，copy 和 update 運算式會 `arr w/ idx <- value` 建立新的陣列，並將所有專案設定為中的對應專案 `arr` ，但所指定的元素 (s) `idx` ，這會設定為中) 的 (值 `value` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="1bf26-296">指定 `arr` 的包含陣列 `[0,1,2,3]` ，然後</span><span class="sxs-lookup"><span data-stu-id="1bf26-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="1bf26-297">`arr w/ 0 <- 10`是陣列 `[10,1,2,3]` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="1bf26-298">`arr w/ 2 <- 10`是陣列 `[0,1,10,3]` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="1bf26-299">`arr w/ 0..2..3 <- [10,12]`是陣列 `[10,1,12,3]` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="1bf26-300">已命名專案的複製和更新運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="1bf26-301">使用者定義類型中的命名專案有類似的運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="1bf26-302">例如，請考慮類型</span><span class="sxs-lookup"><span data-stu-id="1bf26-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="1bf26-303">如果 `c` 包含型別的值 `Complex(1., -1.)` ，則 `c w/ Re <- 0.` 為評估為之型別的運算式 `Complex` `Complex(0., -1.)` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="1bf26-304">不規則陣列</span><span class="sxs-lookup"><span data-stu-id="1bf26-304">Jagged Arrays</span></span>

<span data-ttu-id="1bf26-305">不規則陣列（有時稱為「陣列」陣列）是其元素為數組的陣列。</span><span class="sxs-lookup"><span data-stu-id="1bf26-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="1bf26-306">不規則陣列的元素可以是不同的大小。</span><span class="sxs-lookup"><span data-stu-id="1bf26-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="1bf26-307">下列範例顯示如何宣告和初始化代表乘法資料表的不規則陣列。</span><span class="sxs-lookup"><span data-stu-id="1bf26-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="1bf26-308">Callables 的陣列</span><span class="sxs-lookup"><span data-stu-id="1bf26-308">Arrays of callables</span></span> 

<span data-ttu-id="1bf26-309">您也可以建立 callables 的陣列。</span><span class="sxs-lookup"><span data-stu-id="1bf26-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="1bf26-310">如果一般專案類型是作業或函式類型，所有元素都必須具有相同的輸入和輸出類型。</span><span class="sxs-lookup"><span data-stu-id="1bf26-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="1bf26-311">陣列的元素類型支援所有元素都支援的任何[函子](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="1bf26-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="1bf26-312">例如，如果 `Op1` 、 `Op2` 和 `Op3` 全都是 `Qubit[] => Unit` 作業，但 `Op1` 支援、支援 `Adjoint` `Op2` `Controlled` 和 `Op3` 兩者都支援：</span><span class="sxs-lookup"><span data-stu-id="1bf26-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="1bf26-313">`[Op1, Op2]`是作業的陣列 `(Qubit[] => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="1bf26-314">`[Op1, Op3]`是作業的陣列 `(Qubit[] => Unit is Adj)` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="1bf26-315">`[Op2, Op3]`是作業的陣列 `(Qubit[] => Unit is Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="1bf26-316">不過，雖然作業 `(Qubit[] => Unit is Adj)` 和 `(Qubit[] => Unit is Ctl)` 具有的通用基底類型 `(Qubit[] => Unit)` ，但這些作業的*陣列*並不會共用通用基底類型。</span><span class="sxs-lookup"><span data-stu-id="1bf26-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="1bf26-317">例如， `[[Op1], [Op2]]` 目前會引發錯誤，因為它會嘗試建立兩個不相容陣列類型和的陣列 `(Qubit[] => Unit is Adj)[]` `(Qubit[] => Unit is Ctl)[]` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="1bf26-318">如需 callables 的詳細資訊，請參閱此頁面上的可呼叫[運算式](#callable-expressions)或[ Q# 中的作業和](xref:microsoft.quantum.guide.operationsfunctions)函式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="1bf26-319">條件運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-319">Conditional Expressions</span></span>

<span data-ttu-id="1bf26-320">假設有兩個相同類型的運算式和一個布林運算式，請使用問號、和分隔號來形成條件運算式 `?` `|` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="1bf26-321">指定時 `a==b ? c | d` ， `c` 如果為 true，則條件運算式的值為，如果為 false，則為 `a==b` `d` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="1bf26-322">具有 callables 的條件運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-322">Conditional expressions with callables</span></span>

<span data-ttu-id="1bf26-323">條件運算式可能會評估為具有相同輸入和輸出的作業，但支援不同的函子。</span><span class="sxs-lookup"><span data-stu-id="1bf26-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="1bf26-324">在此情況下，條件運算式的類型是具有輸入和輸出的作業，可支援這兩個運算式所支援的任何函子。</span><span class="sxs-lookup"><span data-stu-id="1bf26-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="1bf26-325">例如，如果、和都是，則支援、和支援 `Op1` `Op2` `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` 兩者：</span><span class="sxs-lookup"><span data-stu-id="1bf26-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="1bf26-326">`flag ? Op1 | Op2`這是一種作業 `(Qubit[] => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="1bf26-327">`flag ? Op1 | Op3`這是一種作業 `(Qubit[] => Unit is Adj)` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="1bf26-328">`flag ? Op2 | Op3`這是一種作業 `(Qubit[] => Unit is Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="1bf26-329">如果兩個可能的結果運算式中有一個包含函式或作業呼叫，該呼叫只會在該結果是呼叫的值時才會發生。</span><span class="sxs-lookup"><span data-stu-id="1bf26-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="1bf26-330">例如，在案例中 `a==b ? C(qs) | D(qs)` ，如果 `a==b` 為 true，則會叫用作業 `C` ，如果是 false，則只 `D` 會叫用作業。</span><span class="sxs-lookup"><span data-stu-id="1bf26-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="1bf26-331">這個方法類似于其他語言的*簡短*運算。</span><span class="sxs-lookup"><span data-stu-id="1bf26-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="1bf26-332">可呼叫的運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-332">Callable Expressions</span></span>

<span data-ttu-id="1bf26-333">可呼叫的常值是在編譯範圍中定義的作業或函式的名稱。</span><span class="sxs-lookup"><span data-stu-id="1bf26-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="1bf26-334">例如， `X` 是參考標準程式庫作業的作業常值 `X` ，而 `Message` 是參考標準程式庫函數的函式常值 `Message` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="1bf26-335">如果作業支援 `Adjoint` 仿函數，則為作業 `Adjoint op` 運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="1bf26-336">同樣地，如果作業支援 `Controlled` 仿函數，則 `Controlled op` 是作業運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="1bf26-337">如需這些運算式類型的詳細資訊，請參閱[呼叫](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)作業特製化。</span><span class="sxs-lookup"><span data-stu-id="1bf26-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="1bf26-338">除了解除 `Adjoint` `Controlled` 包裝運算子和使用的陣列索引以外，函子 (和) 系結比其他所有運算子更緊密 `!` `[ ]` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="1bf26-339">因此，下列各項都是有效的，假設作業支援使用的函子：</span><span class="sxs-lookup"><span data-stu-id="1bf26-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="1bf26-340">型別參數化可呼叫運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="1bf26-341">您可以使用可呼叫的常值做為值，例如，將它指派給變數，或將它傳遞給另一個可呼叫的。</span><span class="sxs-lookup"><span data-stu-id="1bf26-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="1bf26-342">在此情況下，如果可呼叫的[型別參數](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)，您就必須提供參數做為可呼叫值的一部分。</span><span class="sxs-lookup"><span data-stu-id="1bf26-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="1bf26-343">可呼叫的值不能有任何未指定的類型參數。</span><span class="sxs-lookup"><span data-stu-id="1bf26-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="1bf26-344">例如，如果是具有簽章的函式 `Fun` `'T1->Unit` ：</span><span class="sxs-lookup"><span data-stu-id="1bf26-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="1bf26-345">可呼叫的調用運算式</span><span class="sxs-lookup"><span data-stu-id="1bf26-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="1bf26-346">假設有一個可呼叫的運算式 (作業或函式) 以及可呼叫的簽章之輸入類型的元組運算式，您就可以將元組運算式附加至可呼叫的運算式，以形成*調用運算式*。</span><span class="sxs-lookup"><span data-stu-id="1bf26-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="1bf26-347">調用運算式的類型是可呼叫的簽章的輸出類型。</span><span class="sxs-lookup"><span data-stu-id="1bf26-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="1bf26-348">例如，如果是具有簽章的作業 `Op` `((Int, Qubit) => Double)` ， `Op(3, qubit1)` 就是類型的運算式 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="1bf26-349">同樣地，如果是具有簽章的 `Sin` 函數 `(Double -> Double)` ， `Sin(0.1)` 則是類型的運算式 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="1bf26-350">最後，如果是具有簽章的函式 `Builder` `(Int -> (Int -> Int))` ，則 `Builder(3)` 是從到的函數 `Int` `Int` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="1bf26-351">叫用可呼叫值運算式的結果時，需要一組額外的括弧括住可呼叫的運算式。</span><span class="sxs-lookup"><span data-stu-id="1bf26-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="1bf26-352">因此，若要叫 `Builder` 用從上一段呼叫的結果，正確的語法為：</span><span class="sxs-lookup"><span data-stu-id="1bf26-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="1bf26-353">叫用[型別參數化](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)可呼叫時，您可以在可呼叫運算式之後的角括弧內指定實際的型別參數 `< >` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="1bf26-354">此動作通常不是必要的，因為 Q# 編譯器會推斷實際的類型。</span><span class="sxs-lookup"><span data-stu-id="1bf26-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="1bf26-355">不過，如果未指定型別參數化引數，[部分應用程式](xref:microsoft.quantum.guide.operationsfunctions#partial-application)*就*需要此參數。</span><span class="sxs-lookup"><span data-stu-id="1bf26-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="1bf26-356">將具有不同仿函數支援的作業傳遞給可呼叫的時，它也很有用。</span><span class="sxs-lookup"><span data-stu-id="1bf26-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="1bf26-357">例如，如果有簽章，且具有簽章，且具有簽章 `Func` `('T1, 'T2, 'T1) -> 'T2` ，則 `Op1` `Op2` 會 `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` 以 `Func` `Op1` 做為第一個引數來叫用， `Op2` 第二個是，而 `Op3` 第三個是：</span><span class="sxs-lookup"><span data-stu-id="1bf26-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="1bf26-358">類型規格是必要的，因為 `Op3` 和 `Op1` 具有不同的類型，因此編譯器會將此視為不明確的指定。</span><span class="sxs-lookup"><span data-stu-id="1bf26-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="1bf26-359">運算子優先順序</span><span class="sxs-lookup"><span data-stu-id="1bf26-359">Operator Precedence</span></span>

* <span data-ttu-id="1bf26-360">除了之外，所有二元運算子都是右向關聯 `^` 。</span><span class="sxs-lookup"><span data-stu-id="1bf26-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="1bf26-361">以方括弧括住 `[ ]` 陣列切割和索引，並在任何運算子之前系結。</span><span class="sxs-lookup"><span data-stu-id="1bf26-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="1bf26-362">在 `Adjoint` `Controlled` 陣列索引後，但在其他所有運算子之前的函子和系結。</span><span class="sxs-lookup"><span data-stu-id="1bf26-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="1bf26-363">運算和函式呼叫的括弧也會系結在任何運算子之前，但是在陣列索引和函子之後。</span><span class="sxs-lookup"><span data-stu-id="1bf26-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="1bf26-364">Q#依優先順序排列的運算子，從最高到最低：</span><span class="sxs-lookup"><span data-stu-id="1bf26-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="1bf26-365">運算子</span><span class="sxs-lookup"><span data-stu-id="1bf26-365">Operator</span></span> | <span data-ttu-id="1bf26-366">Arity</span><span class="sxs-lookup"><span data-stu-id="1bf26-366">Arity</span></span> | <span data-ttu-id="1bf26-367">描述</span><span class="sxs-lookup"><span data-stu-id="1bf26-367">Description</span></span> | <span data-ttu-id="1bf26-368">運算元類型</span><span class="sxs-lookup"><span data-stu-id="1bf26-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="1bf26-369">句號`!`</span><span class="sxs-lookup"><span data-stu-id="1bf26-369">trailing `!`</span></span> | <span data-ttu-id="1bf26-370">一元 (Unary)</span><span class="sxs-lookup"><span data-stu-id="1bf26-370">Unary</span></span> | <span data-ttu-id="1bf26-371">解除包裝</span><span class="sxs-lookup"><span data-stu-id="1bf26-371">Unwrap</span></span> | <span data-ttu-id="1bf26-372">任何使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="1bf26-372">Any user-defined type</span></span>
 <span data-ttu-id="1bf26-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="1bf26-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="1bf26-374">一元 (Unary)</span><span class="sxs-lookup"><span data-stu-id="1bf26-374">Unary</span></span> | <span data-ttu-id="1bf26-375">數值負數、位補數、邏輯否定</span><span class="sxs-lookup"><span data-stu-id="1bf26-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="1bf26-376">`Int`、 `BigInt` 或 `Double` 為 `-` ， `Int` 或 `BigInt` `~~~` 代表 `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="1bf26-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="1bf26-377">Binary</span><span class="sxs-lookup"><span data-stu-id="1bf26-377">Binary</span></span> | <span data-ttu-id="1bf26-378">整數乘冪</span><span class="sxs-lookup"><span data-stu-id="1bf26-378">Integer power</span></span> | <span data-ttu-id="1bf26-379">`Int`或 `BigInt` 作為基底， `Int` 代表指數</span><span class="sxs-lookup"><span data-stu-id="1bf26-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="1bf26-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="1bf26-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="1bf26-381">Binary</span><span class="sxs-lookup"><span data-stu-id="1bf26-381">Binary</span></span> | <span data-ttu-id="1bf26-382">除法、乘法、integer 模數</span><span class="sxs-lookup"><span data-stu-id="1bf26-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="1bf26-383">`Int`、 `BigInt` 或 `Double` 適用于 `/` 和 `*` ， `Int` 或 `BigInt` 為`%`</span><span class="sxs-lookup"><span data-stu-id="1bf26-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="1bf26-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="1bf26-384">`+`, `-`</span></span> | <span data-ttu-id="1bf26-385">Binary</span><span class="sxs-lookup"><span data-stu-id="1bf26-385">Binary</span></span> | <span data-ttu-id="1bf26-386">加法或字串和陣列串連，減法</span><span class="sxs-lookup"><span data-stu-id="1bf26-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="1bf26-387">`Int`、 `BigInt` 或 `Double` ，此外 `String` 或任何的陣列類型`+`</span><span class="sxs-lookup"><span data-stu-id="1bf26-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="1bf26-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="1bf26-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="1bf26-389">Binary</span><span class="sxs-lookup"><span data-stu-id="1bf26-389">Binary</span></span> | <span data-ttu-id="1bf26-390">左 shift、right shift</span><span class="sxs-lookup"><span data-stu-id="1bf26-390">Left shift, right shift</span></span> | <span data-ttu-id="1bf26-391">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1bf26-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="1bf26-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="1bf26-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="1bf26-393">Binary</span><span class="sxs-lookup"><span data-stu-id="1bf26-393">Binary</span></span> | <span data-ttu-id="1bf26-394">小於、小於或等於、大於、大於、等於或相等的比較</span><span class="sxs-lookup"><span data-stu-id="1bf26-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="1bf26-395">`Int`、 `BigInt` 或`Double`</span><span class="sxs-lookup"><span data-stu-id="1bf26-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="1bf26-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="1bf26-396">`==`, `!=`</span></span> | <span data-ttu-id="1bf26-397">Binary</span><span class="sxs-lookup"><span data-stu-id="1bf26-397">Binary</span></span> | <span data-ttu-id="1bf26-398">等於、不等於比較</span><span class="sxs-lookup"><span data-stu-id="1bf26-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="1bf26-399">任何基本類型</span><span class="sxs-lookup"><span data-stu-id="1bf26-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="1bf26-400">Binary</span><span class="sxs-lookup"><span data-stu-id="1bf26-400">Binary</span></span> | <span data-ttu-id="1bf26-401">位元 AND</span><span class="sxs-lookup"><span data-stu-id="1bf26-401">Bitwise AND</span></span> | <span data-ttu-id="1bf26-402">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1bf26-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="1bf26-403">Binary</span><span class="sxs-lookup"><span data-stu-id="1bf26-403">Binary</span></span> | <span data-ttu-id="1bf26-404">位元 XOR</span><span class="sxs-lookup"><span data-stu-id="1bf26-404">Bitwise XOR</span></span> | <span data-ttu-id="1bf26-405">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1bf26-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="1bf26-406">Binary</span><span class="sxs-lookup"><span data-stu-id="1bf26-406">Binary</span></span> | <span data-ttu-id="1bf26-407">位元 OR</span><span class="sxs-lookup"><span data-stu-id="1bf26-407">Bitwise OR</span></span> | <span data-ttu-id="1bf26-408">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1bf26-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="1bf26-409">Binary</span><span class="sxs-lookup"><span data-stu-id="1bf26-409">Binary</span></span> | <span data-ttu-id="1bf26-410">邏輯 AND</span><span class="sxs-lookup"><span data-stu-id="1bf26-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="1bf26-411">Binary</span><span class="sxs-lookup"><span data-stu-id="1bf26-411">Binary</span></span> | <span data-ttu-id="1bf26-412">邏輯 OR</span><span class="sxs-lookup"><span data-stu-id="1bf26-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="1bf26-413">Binary/三元</span><span class="sxs-lookup"><span data-stu-id="1bf26-413">Binary/Ternary</span></span> | <span data-ttu-id="1bf26-414">Range 運算子</span><span class="sxs-lookup"><span data-stu-id="1bf26-414">Range operator</span></span> | `Int`
 <span data-ttu-id="1bf26-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="1bf26-415">`?` `|`</span></span> | <span data-ttu-id="1bf26-416">三元</span><span class="sxs-lookup"><span data-stu-id="1bf26-416">Ternary</span></span> | <span data-ttu-id="1bf26-417">條件式</span><span class="sxs-lookup"><span data-stu-id="1bf26-417">Conditional</span></span> | <span data-ttu-id="1bf26-418">`Bool`左側的</span><span class="sxs-lookup"><span data-stu-id="1bf26-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="1bf26-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="1bf26-419">`w/` `<-`</span></span> | <span data-ttu-id="1bf26-420">三元</span><span class="sxs-lookup"><span data-stu-id="1bf26-420">Ternary</span></span> | <span data-ttu-id="1bf26-421">複製和更新</span><span class="sxs-lookup"><span data-stu-id="1bf26-421">Copy-and-update</span></span> | <span data-ttu-id="1bf26-422">請參閱[複製和更新運算式](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="1bf26-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="1bf26-423">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1bf26-423">Next steps</span></span>

<span data-ttu-id="1bf26-424">現在您可以使用中的運算式 Q# ，請移至[中 Q# 的作業和](xref:microsoft.quantum.guide.operationsfunctions)函式，以瞭解如何定義和呼叫作業和函數。</span><span class="sxs-lookup"><span data-stu-id="1bf26-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
