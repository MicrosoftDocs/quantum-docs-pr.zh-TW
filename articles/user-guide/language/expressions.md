---
title: Q 中的類型運算式#
description: '瞭解如何指定、參考和合併常數、變數、運算子、作業和函數，做為 Q # 中的運算式。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: b32644382bb88fb11da00d0d7d78bbd797a0eaaa
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84629987"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="6dce7-103">Q 中的類型運算式#</span><span class="sxs-lookup"><span data-stu-id="6dce7-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="6dce7-104">數值運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-104">Numeric Expressions</span></span>

<span data-ttu-id="6dce7-105">數值運算式是、或類型的運算式 `Int` `BigInt` `Double` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="6dce7-106">也就是說，它們可以是整數或浮點數。</span><span class="sxs-lookup"><span data-stu-id="6dce7-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="6dce7-107">`Int`Q # 中的常值只會以一連串的數位撰寫。</span><span class="sxs-lookup"><span data-stu-id="6dce7-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="6dce7-108">使用和前置詞分別支援十六進位和二進位整數 `0x` `0b` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="6dce7-109">`BigInt`Q # 中的常值是以尾端或後置字元寫入 `l` `L` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="6dce7-110">十六進位大整數支援 "0x" 前置詞。</span><span class="sxs-lookup"><span data-stu-id="6dce7-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="6dce7-111">因此，下列是常值的所有有效用法 `BigInt` ：</span><span class="sxs-lookup"><span data-stu-id="6dce7-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="6dce7-112">`Double`Q # 中的常值是使用十進位數撰寫的浮點數。</span><span class="sxs-lookup"><span data-stu-id="6dce7-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="6dce7-113">它們可以使用小數點、 `.` 和（或）以 ' e ' 或 ' e ' 表示的指數部分進行寫入（在此之後，只有可能的負號和十進位數有效）。</span><span class="sxs-lookup"><span data-stu-id="6dce7-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="6dce7-114">下列是有效的 `Double` 常值： `0.0` 、 `1.2e5` 、 `1e-5` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="6dce7-115">假設有任何元素類型的陣列運算式，則可以 `Int` 使用內建函數來形成運算式， [`Length`](xref:microsoft.quantum.core.length) 並以括弧括住陣列運算式 `(` 和 `)` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="6dce7-116">例如，如果系結 `a` 至陣列，則 `Length(a)` 為整數運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="6dce7-117">如果 `b` 是整數陣列的陣列， `Int[][]` 則 `Length(b)` 是中的子陣列數目 `b` ，而 `Length(b[1])` 是中第二個子陣列中的整數數目 `b` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="6dce7-118">假設有兩個相同類型的數值運算式，則 `+` 可以使用二元運算子、、 `-` `*` 和 `/` 來形成新的數值運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="6dce7-119">新運算式的類型會與組成運算式的類型相同。</span><span class="sxs-lookup"><span data-stu-id="6dce7-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="6dce7-120">假設有兩個整數運算式， `^` 可以使用二元運算子（乘冪）來形成新的整數運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="6dce7-121">同樣地， `^` 可以搭配兩個雙重運算式使用，以形成新的 double 運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="6dce7-122">最後， `^` 可以搭配左邊的大整數和右邊的整數來形成新的大整數運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="6dce7-123">在此情況下，第二個參數必須符合32位;如果不是，則會引發執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="6dce7-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="6dce7-124">假設有兩個整數或大整數運算式，則可以使用 `%` （模數）、 `&&&` （位 and）、 `|||` （位 or）或 `^^^` （位 XOR）運算子來形成新的整數或大整數運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="6dce7-125">指定左邊的整數或大整數運算式，以及右邊的整數運算式時， `<<<` 可以使用（算術左移位）或 `>>>` （算術右移位）運算子，來建立與左邊運算式具有相同類型的新運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="6dce7-126">轉換作業的第二個參數（移位量）必須大於或等於零;負位移金額的行為未定義。</span><span class="sxs-lookup"><span data-stu-id="6dce7-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="6dce7-127">任何移位作業的移位量也必須符合32位;如果不是，則會引發執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="6dce7-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="6dce7-128">如果要移動的數位是整數，則會解讀移位量 `mod 64` ; 也就是說，1和位移65的位移具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="6dce7-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="6dce7-129">對於整數和大整數值，移位是算術。</span><span class="sxs-lookup"><span data-stu-id="6dce7-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="6dce7-130">將負數值向左或右移位會產生負數。</span><span class="sxs-lookup"><span data-stu-id="6dce7-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="6dce7-131">也就是，將一個步驟向左或向右移位，與分別為乘法或除以2的方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="6dce7-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="6dce7-132">整數除法和整數模數會遵循與 c # 相同的負數行為。</span><span class="sxs-lookup"><span data-stu-id="6dce7-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="6dce7-133">也就是， `a % b` 一律會有相同的正負號 `a` ，而且 `b * (a / b) + a % b` 一定會相等 `a` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="6dce7-134">例如：</span><span class="sxs-lookup"><span data-stu-id="6dce7-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="6dce7-135">5</span><span class="sxs-lookup"><span data-stu-id="6dce7-135">5</span></span> | <span data-ttu-id="6dce7-136">2</span><span class="sxs-lookup"><span data-stu-id="6dce7-136">2</span></span> | <span data-ttu-id="6dce7-137">2</span><span class="sxs-lookup"><span data-stu-id="6dce7-137">2</span></span> | <span data-ttu-id="6dce7-138">1</span><span class="sxs-lookup"><span data-stu-id="6dce7-138">1</span></span>
 <span data-ttu-id="6dce7-139">5</span><span class="sxs-lookup"><span data-stu-id="6dce7-139">5</span></span> | <span data-ttu-id="6dce7-140">-2</span><span class="sxs-lookup"><span data-stu-id="6dce7-140">-2</span></span> | <span data-ttu-id="6dce7-141">-2</span><span class="sxs-lookup"><span data-stu-id="6dce7-141">-2</span></span> | <span data-ttu-id="6dce7-142">1</span><span class="sxs-lookup"><span data-stu-id="6dce7-142">1</span></span>
 <span data-ttu-id="6dce7-143">-5</span><span class="sxs-lookup"><span data-stu-id="6dce7-143">-5</span></span> | <span data-ttu-id="6dce7-144">2</span><span class="sxs-lookup"><span data-stu-id="6dce7-144">2</span></span> | <span data-ttu-id="6dce7-145">-2</span><span class="sxs-lookup"><span data-stu-id="6dce7-145">-2</span></span> | <span data-ttu-id="6dce7-146">-1</span><span class="sxs-lookup"><span data-stu-id="6dce7-146">-1</span></span>
 <span data-ttu-id="6dce7-147">-5</span><span class="sxs-lookup"><span data-stu-id="6dce7-147">-5</span></span> | <span data-ttu-id="6dce7-148">-2</span><span class="sxs-lookup"><span data-stu-id="6dce7-148">-2</span></span> | <span data-ttu-id="6dce7-149">2</span><span class="sxs-lookup"><span data-stu-id="6dce7-149">2</span></span> | <span data-ttu-id="6dce7-150">-1</span><span class="sxs-lookup"><span data-stu-id="6dce7-150">-1</span></span>

<span data-ttu-id="6dce7-151">大整數除法和模數的運作方式相同。</span><span class="sxs-lookup"><span data-stu-id="6dce7-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="6dce7-152">假設有任何數值運算式，可能會使用一元運算子來形成新的運算式 `-` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="6dce7-153">新的運算式將與組成運算式的類型相同。</span><span class="sxs-lookup"><span data-stu-id="6dce7-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="6dce7-154">假設有任何整數或大整數運算式，則可以使用 `~~~` （位補數）一元運算子來形成相同類型的新運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="6dce7-155">布林運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-155">Boolean Expressions</span></span>

<span data-ttu-id="6dce7-156">這兩個 `Bool` 常值為 `true` 和 `false` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="6dce7-157">假設有兩個相同基本類型的運算式，則 `==` 和 `!=` 二元運算子可用來建立 `Bool` 運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="6dce7-158">如果兩個運算式相等，則運算式會是 true，否則為 false。</span><span class="sxs-lookup"><span data-stu-id="6dce7-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="6dce7-159">可能不會比較使用者定義類型的值，只可以比較其未包裝的值。</span><span class="sxs-lookup"><span data-stu-id="6dce7-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="6dce7-160">例如，使用「解除包裝」運算子（如需 `!` 詳細說明，請見[Q # 中的類型](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)）。</span><span class="sxs-lookup"><span data-stu-id="6dce7-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="6dce7-161">值的相等比較 `Qubit` 是識別相等的，也就是兩個運算式是否識別相同的 qubit。</span><span class="sxs-lookup"><span data-stu-id="6dce7-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="6dce7-162">這兩個 qubits 的狀態不會由這項比較進行比較、存取、測量或修改。</span><span class="sxs-lookup"><span data-stu-id="6dce7-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="6dce7-163">值的相等比較 `Double` 可能會因為進位效果而誤導。</span><span class="sxs-lookup"><span data-stu-id="6dce7-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="6dce7-164">例如， `49.0 * (1.0/49.0) != 1.0` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="6dce7-165">假設有兩個數值運算式， `>` `<` `>=` `<=` 如果第一個運算式分別大於、小於、大於或等於或小於或等於第二個運算式，則二元運算子、、和可能會用來建立新的布林值運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="6dce7-166">假設有兩個布林運算式， `and` 和 `or` 二元運算子可用來建立新的布林運算式，如果這兩個運算式（resp）都是 true，則為 true。</span><span class="sxs-lookup"><span data-stu-id="6dce7-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="6dce7-167">假設有任何布林運算式， `not` 一元運算子可用來建立新的布林運算式，如果組成運算式為 false，則為 true。</span><span class="sxs-lookup"><span data-stu-id="6dce7-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="6dce7-168">字串運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-168">String Expressions</span></span>

<span data-ttu-id="6dce7-169">Q # 允許在 `fail` 語句（在[控制流程](xref:microsoft.quantum.guide.controlflow#fail-statement)中說明）和標準函式中使用字串 [`Message`](xref:microsoft.quantum.intrinsic.message) 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="6dce7-170">後者的特定行為取決於所使用的模擬器，但通常會在問 # 程式期間呼叫時，將訊息寫入主機主控台。</span><span class="sxs-lookup"><span data-stu-id="6dce7-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="6dce7-171">Q # 中的字串可以是常值或字串插值。</span><span class="sxs-lookup"><span data-stu-id="6dce7-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="6dce7-172">字串常值類似于大部分語言中的簡單字串常值：以雙引號括住的 Unicode 字元序列 `"` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="6dce7-173">在字串內，反斜線字元可用來將 `\` 雙引號字元轉義，並插入新行做為 `\n` 、做為的回車 `\r` ，以及做為索引標籤 `\t` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="6dce7-174">例如：</span><span class="sxs-lookup"><span data-stu-id="6dce7-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="6dce7-175">插入字串</span><span class="sxs-lookup"><span data-stu-id="6dce7-175">Interpolated strings</span></span>

<span data-ttu-id="6dce7-176">String 插補的 Q # 語法是 c # 語法的子集，但我們在此摘要說明與 Q # 相關的重點。</span><span class="sxs-lookup"><span data-stu-id="6dce7-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="6dce7-177">主要的區別如下所述。</span><span class="sxs-lookup"><span data-stu-id="6dce7-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="6dce7-178">若要將字串常值識別為插入字串，請在其前面加上 `$` 符號。</span><span class="sxs-lookup"><span data-stu-id="6dce7-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="6dce7-179">`$`開始字串常值的和之間不能有空白字元 `"` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="6dce7-180">以下是使用 [`Message`](xref:microsoft.quantum.intrinsic.message) 函數將測量結果寫入主控台的基本範例，以及其他的 Q # 運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="6dce7-181">任何有效的 Q # 運算式可能會出現在字串插值中。</span><span class="sxs-lookup"><span data-stu-id="6dce7-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="6dce7-182">如需 c # 語法的進一步詳細資料，請參閱[*字串插值*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。</span><span class="sxs-lookup"><span data-stu-id="6dce7-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="6dce7-183">最明顯的差異在於，Q # 不支援逐字（多行）字串插值。</span><span class="sxs-lookup"><span data-stu-id="6dce7-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="6dce7-184">插補字串內的運算式遵循 Q # 語法，而不是 c # 語法。</span><span class="sxs-lookup"><span data-stu-id="6dce7-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="6dce7-185">範圍運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-185">Range Expressions</span></span>

<span data-ttu-id="6dce7-186">假設有任何三個 `Int` 運算式 `start` 、 `step` 和 `stop` ， `start .. step .. stop` 就是一個範圍運算式，其第一個元素是 `start` 、第二個元素是、 `start+step` 第三個元素， `start+step+step` 依此類推，直到 `stop` 傳遞為止。</span><span class="sxs-lookup"><span data-stu-id="6dce7-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="6dce7-187">例如，如果是正數和，範圍可能會是空的 `step` `stop < start` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="6dce7-188">`stop`如果和之間的差異是的整數倍數，則範圍的最後一個元素會是 `start` `stop` `step` ; 也就是說，範圍在兩端都包含在內。</span><span class="sxs-lookup"><span data-stu-id="6dce7-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="6dce7-189">假設有兩個 `Int` 運算式 `start` 和 `stop` ， `start .. stop` 是等於的範圍運算式 `start .. 1 .. stop` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="6dce7-190">請注意， `step` 即使小於，隱含也是 + 1 `stop` `start` ; 在這種情況下，範圍是空的。</span><span class="sxs-lookup"><span data-stu-id="6dce7-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="6dce7-191">一些範例範圍如下：</span><span class="sxs-lookup"><span data-stu-id="6dce7-191">Some example ranges are:</span></span>

- <span data-ttu-id="6dce7-192">`1..3`為1、2、3的範圍。</span><span class="sxs-lookup"><span data-stu-id="6dce7-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="6dce7-193">`2..2..5`是範圍2，4。</span><span class="sxs-lookup"><span data-stu-id="6dce7-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="6dce7-194">`2..2..6`為範圍2、4、6。</span><span class="sxs-lookup"><span data-stu-id="6dce7-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="6dce7-195">`6..-2..2`為6、4、2的範圍。</span><span class="sxs-lookup"><span data-stu-id="6dce7-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="6dce7-196">`2..1`這是空的範圍。</span><span class="sxs-lookup"><span data-stu-id="6dce7-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="6dce7-197">`2..6..7`為範圍2。</span><span class="sxs-lookup"><span data-stu-id="6dce7-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="6dce7-198">`2..2..1`這是空的範圍。</span><span class="sxs-lookup"><span data-stu-id="6dce7-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="6dce7-199">`1..-1..2`這是空的範圍。</span><span class="sxs-lookup"><span data-stu-id="6dce7-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="6dce7-200">Qubit 運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-200">Qubit Expressions</span></span>

<span data-ttu-id="6dce7-201">唯一的 `Qubit` 運算式是系結至 `Qubit` 陣列的值或陣列元素的符號 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="6dce7-202">沒有任何 `Qubit` 常值。</span><span class="sxs-lookup"><span data-stu-id="6dce7-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="6dce7-203">Pauli 運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-203">Pauli Expressions</span></span>

<span data-ttu-id="6dce7-204">、、和這四個 `Pauli` 值 `PauliI` `PauliX` `PauliY` `PauliZ` 都是有效的 `Pauli` 運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="6dce7-205">除了這以外，唯一的 `Pauli` 運算式是系結至 `Pauli` 陣列值或陣列元素的符號 `Pauli` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="6dce7-206">結果運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-206">Result Expressions</span></span>

<span data-ttu-id="6dce7-207">和這兩個 `Result` 值 `One` `Zero` 都是有效的 `Result` 運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="6dce7-208">除了這以外，唯一的 `Result` 運算式是系結至 `Result` 陣列值或陣列元素的符號 `Result` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="6dce7-209">特別要注意的是，與 `One` 整數不相同 `1` ，而且它們之間沒有直接的轉換。</span><span class="sxs-lookup"><span data-stu-id="6dce7-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="6dce7-210">和的情況也是 `Zero` 如此 `0` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="6dce7-211">元組運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-211">Tuple Expressions</span></span>

<span data-ttu-id="6dce7-212">元組常值是適當類型的元素運算式序列，以逗號分隔，並包含在 `(` 和中 `)` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="6dce7-213">例如， `(1, One)` 是 `(Int, Result)` 運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="6dce7-214">除了常值以外，唯一的元組運算式是系結至元組值的符號、元組陣列的陣列元素，以及傳回元組的可呼叫調用。</span><span class="sxs-lookup"><span data-stu-id="6dce7-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="6dce7-215">使用者定義型別運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="6dce7-216">使用者自訂類型的常值是由類型名稱後面接著類型的基礎元組類型的元組常值所組成。</span><span class="sxs-lookup"><span data-stu-id="6dce7-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="6dce7-217">例如，如果 `IntPair` 是以為基礎的使用者定義型別 `(Int, Int)` ，則會 `IntPair(2, 3)` 是該型別的有效常值。</span><span class="sxs-lookup"><span data-stu-id="6dce7-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="6dce7-218">除了常值以外，使用者定義型別的唯一運算式是系結至該型別、該型別陣列的陣列元素，以及傳回該型別之可呼叫調用的符號。</span><span class="sxs-lookup"><span data-stu-id="6dce7-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="6dce7-219">解除包裝運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-219">Unwrap Expressions</span></span>

<span data-ttu-id="6dce7-220">在 Q # 中，解除包裝運算子是尾端驚嘆號 `!` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="6dce7-221">例如，如果 `IntPair` 是具有基礎類型的使用者定義型別 `(Int, Int)` ，而是 `s` 具有值的變數 `IntPair(2, 3)` ，則會 `s!` 是 `(2, 3)` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="6dce7-222">針對其他使用者定義型別所定義的使用者定義型別，可能會重複執行解除包裝運算子;例如， `s!!` 表示的雙重解除包裝值 `s` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-222">For user-defined types defined in terms of other user-defined types, the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="6dce7-223">因此，如果 `WrappedPair` 是具有基礎類型的使用者定義型別 `IntPair` ，而 `t` 是具有值的變數 `WrappedPair(IntPair(1,2))` ，則會 `t!!` 是 `(1,2)` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-223">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="6dce7-224">除了 `!` 陣列索引和切割以外，運算子的優先順序高於其他所有運算子 `[]` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-224">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="6dce7-225">`!`和系結 `[]` positionally; 也就是，您 `a[i]![3]` 應該將 `((a[i])!)[3]` 它視為：取得的 `i` 第個專案，將它解除 `a` 包裝，然後取得未包裝值的第3個元素（必須是陣列）。</span><span class="sxs-lookup"><span data-stu-id="6dce7-225">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="6dce7-226">運算子的優先順序 `!` 有一個可能不明顯的影響。</span><span class="sxs-lookup"><span data-stu-id="6dce7-226">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="6dce7-227">如果函式或作業傳回值，因而解除包裝，則函式或作業呼叫必須以括弧括住，讓引數元組系結至呼叫，而不是系結。</span><span class="sxs-lookup"><span data-stu-id="6dce7-227">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="6dce7-228">例如：</span><span class="sxs-lookup"><span data-stu-id="6dce7-228">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="6dce7-229">陣列運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-229">Array Expressions</span></span>

<span data-ttu-id="6dce7-230">陣列常值是一系列的一或多個元素運算式，並以逗號分隔， `[` 並包含在和中 `]` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-230">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="6dce7-231">所有元素都必須與相同的型別相容。</span><span class="sxs-lookup"><span data-stu-id="6dce7-231">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="6dce7-232">假設有兩個相同類型的陣列，則可以 `+` 使用二元運算子來形成新陣列，這是兩個數組的串連。</span><span class="sxs-lookup"><span data-stu-id="6dce7-232">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="6dce7-233">例如， `[1,2,3] + [4,5,6]` 是 `[1,2,3,4,5,6]` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-233">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="6dce7-234">陣列建立</span><span class="sxs-lookup"><span data-stu-id="6dce7-234">Array Creation</span></span>

<span data-ttu-id="6dce7-235">假設有型別和 `Int` 運算式， `new` 運算子可用來配置指定大小的新陣列。</span><span class="sxs-lookup"><span data-stu-id="6dce7-235">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="6dce7-236">例如， `new Int[i + 1]` 會使用元素配置新的 `Int` 陣列 `i + 1` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-236">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="6dce7-237">不允許空的陣列常值 `[]` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-237">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="6dce7-238">相反 `new ★[0]` 地，使用，其中 `★` 是適合類型的預留位置，可讓建立所需長度為零的陣列。</span><span class="sxs-lookup"><span data-stu-id="6dce7-238">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="6dce7-239">新陣列的元素會初始化為與類型相關的預設值。</span><span class="sxs-lookup"><span data-stu-id="6dce7-239">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="6dce7-240">在大部分情況下，這會是零的部分變化。</span><span class="sxs-lookup"><span data-stu-id="6dce7-240">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="6dce7-241">對於實體參考的 qubits 和 callables 而言，沒有合理的預設值。</span><span class="sxs-lookup"><span data-stu-id="6dce7-241">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="6dce7-242">因此，對於這些類型，預設值為不正確參考，無法使用而不會造成執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="6dce7-242">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="6dce7-243">這類似于 c # 或 JAVA 等語言中的 null 參考。</span><span class="sxs-lookup"><span data-stu-id="6dce7-243">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="6dce7-244">包含 qubits 或 callables 的陣列必須使用非預設值正確地初始化，才可以安全地使用它們的元素。</span><span class="sxs-lookup"><span data-stu-id="6dce7-244">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="6dce7-245">您可以在中找到適當的初始化常式 <xref:microsoft.quantum.arrays> 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-245">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="6dce7-246">每種類型的預設值為：</span><span class="sxs-lookup"><span data-stu-id="6dce7-246">The default values for each type are:</span></span>

<span data-ttu-id="6dce7-247">類型</span><span class="sxs-lookup"><span data-stu-id="6dce7-247">Type</span></span> | <span data-ttu-id="6dce7-248">預設</span><span class="sxs-lookup"><span data-stu-id="6dce7-248">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="6dce7-249">_不正確 qubit_</span><span class="sxs-lookup"><span data-stu-id="6dce7-249">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="6dce7-250">空白範圍，`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="6dce7-250">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="6dce7-251">_可呼叫無效_</span><span class="sxs-lookup"><span data-stu-id="6dce7-251">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="6dce7-252">元組類型會依元素初始化。</span><span class="sxs-lookup"><span data-stu-id="6dce7-252">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="6dce7-253">陣列元素</span><span class="sxs-lookup"><span data-stu-id="6dce7-253">Array Elements</span></span>

<span data-ttu-id="6dce7-254">假設有陣列運算式和 `Int` 運算式，則可以使用 `[` 和陣列元素運算子來形成新的運算式 `]` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-254">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="6dce7-255">新的運算式將與陣列的元素類型相同。</span><span class="sxs-lookup"><span data-stu-id="6dce7-255">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="6dce7-256">例如，如果系結 `a` 至的陣列，則 `Double` `a[4]` 為 `Double` 運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-256">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="6dce7-257">如果陣列運算式不是簡單的識別碼，則必須以括弧括住，才能選取元素。</span><span class="sxs-lookup"><span data-stu-id="6dce7-257">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="6dce7-258">比方說，如果 `a` 和 `b` 都是 s 的陣列 `Int` ，則串連中的元素會表示為：</span><span class="sxs-lookup"><span data-stu-id="6dce7-258">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="6dce7-259">Q # 中的所有陣列都是以零為基底。</span><span class="sxs-lookup"><span data-stu-id="6dce7-259">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="6dce7-260">也就是說，陣列的第一個元素 `a` 一定是 `a[0]` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-260">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="6dce7-261">陣列配量</span><span class="sxs-lookup"><span data-stu-id="6dce7-261">Array Slices</span></span>

<span data-ttu-id="6dce7-262">假設有陣列運算式和 `Range` 運算式，則可以使用和陣列配量運算子來形成新的運算式 `[` `]` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-262">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="6dce7-263">新的運算式會與陣列具有相同的類型，而且會包含由的專案所編制索引的陣列專案 `Range` （依照所定義的順序） `Range` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-263">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="6dce7-264">例如，如果系結 `a` 至的陣列，則 `Double` `a[3..-1..0]` 是 `Double[]` 包含前四個專案的運算式， `a` 但在中出現的順序則相反 `a` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-264">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="6dce7-265">如果 `Range` 是空的，則產生的陣列配量會是長度為零的。</span><span class="sxs-lookup"><span data-stu-id="6dce7-265">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="6dce7-266">就像參考陣列專案一樣，如果陣列運算式不是簡單的識別碼，則必須將它括在括弧內，才能進行配量。</span><span class="sxs-lookup"><span data-stu-id="6dce7-266">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="6dce7-267">如果 `a` 和 `b` 都是的陣列 `Int` ，則串連中的配量會表示為：</span><span class="sxs-lookup"><span data-stu-id="6dce7-267">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="6dce7-268">推斷的開始/結束值</span><span class="sxs-lookup"><span data-stu-id="6dce7-268">Inferred start/end values</span></span>

<span data-ttu-id="6dce7-269">從0.8 版開始，我們支援範圍切割的內容相關運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-269">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="6dce7-270">特別的是，範圍的開始和結束值可能會在範圍切割運算式的內容中省略。</span><span class="sxs-lookup"><span data-stu-id="6dce7-270">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="6dce7-271">在這種情況下，編譯器將會套用下列規則，以推斷範圍的預期分隔符號。</span><span class="sxs-lookup"><span data-stu-id="6dce7-271">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="6dce7-272">例如，如果省略範圍起始值，則推斷的起始值</span><span class="sxs-lookup"><span data-stu-id="6dce7-272">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="6dce7-273">如果未指定任何步驟，或指定的步驟是正數，則為零，而</span><span class="sxs-lookup"><span data-stu-id="6dce7-273">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="6dce7-274">如果指定的步驟是負數，則為已切割陣列的長度減一。</span><span class="sxs-lookup"><span data-stu-id="6dce7-274">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="6dce7-275">如果省略範圍結束值，則推斷的結束值</span><span class="sxs-lookup"><span data-stu-id="6dce7-275">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="6dce7-276">這是已切割陣列的長度減一，如果未指定任何步驟，或指定的步驟是正數，則為，</span><span class="sxs-lookup"><span data-stu-id="6dce7-276">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="6dce7-277">如果指定的步驟是負數，則為零。</span><span class="sxs-lookup"><span data-stu-id="6dce7-277">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="6dce7-278">複製和更新運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-278">Copy-and-Update Expressions</span></span>

<span data-ttu-id="6dce7-279">由於所有的 Q # 類型都是實值型別（qubits 採用有點特殊的角色），因此，當值系結至符號或符號重新系結時，就會建立「複製」。</span><span class="sxs-lookup"><span data-stu-id="6dce7-279">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="6dce7-280">也就是說，問 # 的行為與在指派時建立複本相同。</span><span class="sxs-lookup"><span data-stu-id="6dce7-280">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="6dce7-281">當然，實際上只有相關的部分會在需要時重新建立。</span><span class="sxs-lookup"><span data-stu-id="6dce7-281">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="6dce7-282">這也特別包括陣列。</span><span class="sxs-lookup"><span data-stu-id="6dce7-282">This in particular also includes arrays.</span></span>
<span data-ttu-id="6dce7-283">特別是，不可能更新陣列專案。</span><span class="sxs-lookup"><span data-stu-id="6dce7-283">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="6dce7-284">若要修改現有的陣列，您必須利用*複製和更新*機制。</span><span class="sxs-lookup"><span data-stu-id="6dce7-284">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="6dce7-285">您可以透過*複製和更新*運算式，從現有的陣列建立新的陣列。</span><span class="sxs-lookup"><span data-stu-id="6dce7-285">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="6dce7-286">複製和更新運算式是格式的運算式 `expression1 w/ expression2 <- expression3` ，其中必須 `expression1` 是 `T[]` 某種類型的類型 `T` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-286">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="6dce7-287">第二個 `expression2` 定義要修改之元素的索引（相較于中的陣列） `expression1` ，而且必須是類型的類型 `Int` 或 `Range` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-287">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="6dce7-288">如果 `expression2` 的型別為 `Int` ，則 `expression3` 必須是型別 `T` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-288">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="6dce7-289">如果 `expression2` 的型別為 `Range` ，則 `expression3` 必須是型別 `T[]` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-289">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="6dce7-290">「複製並更新」運算式 `arr w/ idx <- value` 會建立新的陣列，其中所有專案都設定為中的對應專案 `arr` ，但的元素除外 `idx` ，其設定為中的一個 `value` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-290">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="6dce7-291">例如，如果 `arr` 包含陣列 `[0,1,2,3]` ，則</span><span class="sxs-lookup"><span data-stu-id="6dce7-291">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="6dce7-292">`arr w/ 0 <- 10`是陣列 `[10,1,2,3]` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-292">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="6dce7-293">`arr w/ 2 <- 10`是陣列 `[0,1,10,3]` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-293">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="6dce7-294">`arr w/ 0..2..3 <- [10,12]`是陣列 `[10,1,12,3]` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-294">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="6dce7-295">已命名專案的複製和更新運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-295">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="6dce7-296">使用者定義類型中的命名專案有類似的運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-296">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="6dce7-297">請考慮類型的範例</span><span class="sxs-lookup"><span data-stu-id="6dce7-297">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="6dce7-298">如果 `c` 包含型別的值 `Complex(1., -1.)` ，則 `c w/ Re <- 0.` 為評估為之型別的運算式 `Complex` `Complex(0., -1.)` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-298">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="6dce7-299">不規則陣列</span><span class="sxs-lookup"><span data-stu-id="6dce7-299">Jagged Arrays</span></span>

<span data-ttu-id="6dce7-300">不規則陣列（有時稱為「陣列」陣列）是其元素為數組的陣列。</span><span class="sxs-lookup"><span data-stu-id="6dce7-300">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="6dce7-301">不規則陣列的元素可以是不同的大小。</span><span class="sxs-lookup"><span data-stu-id="6dce7-301">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="6dce7-302">下列範例顯示如何宣告和初始化代表乘法資料表的不規則陣列。</span><span class="sxs-lookup"><span data-stu-id="6dce7-302">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="6dce7-303">Callables 的陣列</span><span class="sxs-lookup"><span data-stu-id="6dce7-303">Arrays of callables</span></span> 

<span data-ttu-id="6dce7-304">請注意，如需可呼叫類型的詳細資訊，請參閱以下的，以及在 Q # 中的下一頁、[作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="6dce7-304">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="6dce7-305">如果一般專案類型是作業或函式類型，所有元素都必須具有相同的輸入和輸出類型。</span><span class="sxs-lookup"><span data-stu-id="6dce7-305">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="6dce7-306">陣列的元素類型會支援所有元素所支援的任何函子。</span><span class="sxs-lookup"><span data-stu-id="6dce7-306">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="6dce7-307">例如，如果、和都是，則支援、和支援 `Op1` `Op2` `Op3` `Qubit[] => Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` 兩者：</span><span class="sxs-lookup"><span data-stu-id="6dce7-307">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="6dce7-308">`[Op1, Op2]`是作業的陣列 `(Qubit[] => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-308">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="6dce7-309">`[Op1, Op3]`是作業的陣列 `(Qubit[] => Unit is Adj)` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-309">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="6dce7-310">`[Op2, Op3]`是作業的陣列 `(Qubit[] => Unit is Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-310">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="6dce7-311">不過，雖然 `(Qubit[] => Unit is Adj)` 和 `(Qubit[] => Unit is Ctl)` 作業具有的通用基底類型 `(Qubit[] => Unit)` ，但請注意，這些運算子*的*陣列並不會共用通用基底類型。</span><span class="sxs-lookup"><span data-stu-id="6dce7-311">However, while `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` operations have the common base type of `(Qubit[] => Unit)`, note that arrays *of* these operators do not share a common base type.</span></span> <span data-ttu-id="6dce7-312">例如， `[[Op1], [Op2]]` 目前會引發錯誤，因為它正嘗試建立不相容陣列類型和的陣列 `(Qubit[] => Unit is Adj)[]` `(Qubit[] => Unit is Ctl)[]` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-312">For example, `[[Op1], [Op2]]` would currently raise an error because it is attempting to create an array of the incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="6dce7-313">條件運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-313">Conditional Expressions</span></span>

<span data-ttu-id="6dce7-314">假設有兩個相同類型和布林運算式的其他運算式，則可以使用問號和分隔號來形成條件運算式 `?` `|` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-314">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="6dce7-315">例如， `a==b ? c | d` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-315">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="6dce7-316">在此範例中，條件運算式的值會是， `c` 如果 `a==b` 為 true，則為，如果為 false，則為 `d` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-316">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="6dce7-317">具有 callables 的條件運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-317">Conditional expressions with callables</span></span>

<span data-ttu-id="6dce7-318">這兩個運算式可能會評估為具有相同輸入和輸出但支援不同函子的作業。</span><span class="sxs-lookup"><span data-stu-id="6dce7-318">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="6dce7-319">在此情況下，條件運算式的類型是具有這些輸入和輸出的作業，可支援這兩個運算式所支援的任何函子。</span><span class="sxs-lookup"><span data-stu-id="6dce7-319">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="6dce7-320">例如，如果、和都是，則支援、和支援 `Op1` `Op2` `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` 兩者：</span><span class="sxs-lookup"><span data-stu-id="6dce7-320">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="6dce7-321">`flag ? Op1 | Op2`這是一種作業 `(Qubit[] => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-321">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="6dce7-322">`flag ? Op1 | Op3`這是一種作業 `(Qubit[] => Unit is Adj)` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-322">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="6dce7-323">`flag ? Op2 | Op3`這是一種作業 `(Qubit[] => Unit is Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-323">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="6dce7-324">如果兩個可能的結果運算式中有一個包含函式或作業呼叫，只有當該結果是將成為呼叫值的呼叫時，才會進行該呼叫。</span><span class="sxs-lookup"><span data-stu-id="6dce7-324">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="6dce7-325">例如，在案例中 `a==b ? C(qs) | D(qs)` ，如果為 true，則會叫用作業 `a==b` `C` ，如果它是 false，則只 `D` 會叫用。</span><span class="sxs-lookup"><span data-stu-id="6dce7-325">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="6dce7-326">這類似于其他語言的簡短運算。</span><span class="sxs-lookup"><span data-stu-id="6dce7-326">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="6dce7-327">可呼叫的運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-327">Callable Expressions</span></span>

<span data-ttu-id="6dce7-328">可呼叫的常值是在編譯範圍中定義的作業或函式的名稱。</span><span class="sxs-lookup"><span data-stu-id="6dce7-328">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="6dce7-329">例如， `X` 是參考標準程式庫作業的作業常值 `X` ，而 `Message` 是參考標準程式庫函數的函式常值 `Message` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-329">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="6dce7-330">如果作業支援 `Adjoint` 仿函數，則為作業 `Adjoint op` 運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-330">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="6dce7-331">同樣地，如果作業支援 `Controlled` 仿函數，則 `Controlled op` 是作業運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-331">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="6dce7-332">這些運算式的類型是在[呼叫](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)作業特製化時指定。</span><span class="sxs-lookup"><span data-stu-id="6dce7-332">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="6dce7-333">除了解除 `Adjoint` `Controlled` 包裝運算子 `!` 和使用 [] ' 的陣列索引編制以外，函子（和）系結比其他所有運算子更緊密。</span><span class="sxs-lookup"><span data-stu-id="6dce7-333">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="6dce7-334">因此，假設作業支援使用的函子，則下列各項都是合法的：</span><span class="sxs-lookup"><span data-stu-id="6dce7-334">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="6dce7-335">型別參數化可呼叫運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-335">Type-parameterized callable expressions</span></span>

<span data-ttu-id="6dce7-336">可呼叫的常值可用來做為值，比方說，是指派給變數或傳遞給另一個可呼叫的。</span><span class="sxs-lookup"><span data-stu-id="6dce7-336">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="6dce7-337">在此情況下，如果可呼叫的[型別參數](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)為，則必須將它們提供作為可呼叫值的一部分。</span><span class="sxs-lookup"><span data-stu-id="6dce7-337">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="6dce7-338">可呼叫的值不能有任何未指定的類型參數。</span><span class="sxs-lookup"><span data-stu-id="6dce7-338">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="6dce7-339">例如，如果是具有簽章的函式 `Fun` `'T1->Unit` ：</span><span class="sxs-lookup"><span data-stu-id="6dce7-339">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="6dce7-340">可呼叫的調用運算式</span><span class="sxs-lookup"><span data-stu-id="6dce7-340">Callable Invocation Expressions</span></span>

<span data-ttu-id="6dce7-341">假設可呼叫的（作業或函式）運算式，以及可呼叫的簽章之輸入類型的元組運算式，則可以將元組運算式附加至可呼叫的運算式，藉以形成調用運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-341">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="6dce7-342">調用運算式的類型是可呼叫的簽章的輸出類型。</span><span class="sxs-lookup"><span data-stu-id="6dce7-342">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="6dce7-343">例如，如果是具有簽章的作業 `Op` `((Int, Qubit) => Double)` ， `Op(3, qubit1)` 就是類型的運算式 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-343">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="6dce7-344">同樣地，如果是具有簽章的 `Sin` 函數 `(Double -> Double)` ， `Sin(0.1)` 則是類型的運算式 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-344">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="6dce7-345">最後，如果是具有簽章的函式 `Builder` `(Int -> (Int -> Int))` ，則 `Builder(3)` 是從到 Int 的函式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-345">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="6dce7-346">叫用可呼叫值運算式的結果時，需要一組額外的括弧括住可呼叫的運算式。</span><span class="sxs-lookup"><span data-stu-id="6dce7-346">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="6dce7-347">因此，若要叫 `Builder` 用從上一段呼叫的結果，正確的語法為：</span><span class="sxs-lookup"><span data-stu-id="6dce7-347">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="6dce7-348">叫用[型別參數化](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)可呼叫時，可以在角括弧內以及可呼叫 `<` 運算式之後指定實際的型別參數 `>` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-348">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="6dce7-349">這通常是不必要的，因為 Q # 編譯器會推斷實際的類型。</span><span class="sxs-lookup"><span data-stu-id="6dce7-349">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="6dce7-350">不過，如果未指定型別參數化引數，[部分應用程式](xref:microsoft.quantum.guide.operationsfunctions#partial-application)*就*需要此參數。</span><span class="sxs-lookup"><span data-stu-id="6dce7-350">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="6dce7-351">當將具有不同仿函數支援的作業傳遞至可呼叫的時，它有時也很有用。</span><span class="sxs-lookup"><span data-stu-id="6dce7-351">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="6dce7-352">例如，如果有簽章，且具有簽章，且具有簽章 `Func` `('T1, 'T2, 'T1) -> 'T2` ，則 `Op1` `Op2` 會 `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` 以 `Func` `Op1` 做為第一個引數來叫用， `Op2` 第二個是，而當做 `Op3` 第三個：</span><span class="sxs-lookup"><span data-stu-id="6dce7-352">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="6dce7-353">類型規格是必要的，因為 `Op3` 和 `Op1` 具有不同的類型，因此編譯器會將此視為不明確的指定。</span><span class="sxs-lookup"><span data-stu-id="6dce7-353">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="6dce7-354">運算子優先順序</span><span class="sxs-lookup"><span data-stu-id="6dce7-354">Operator Precedence</span></span>

<span data-ttu-id="6dce7-355">除了之外，所有二元運算子都是右向關聯 `^` 。</span><span class="sxs-lookup"><span data-stu-id="6dce7-355">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="6dce7-356">如果是 `[` `]` 陣列切割和編制索引，請在任何運算子之前系結，並以方括弧括住。</span><span class="sxs-lookup"><span data-stu-id="6dce7-356">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="6dce7-357">在 `Adjoint` `Controlled` 陣列索引後，但在其他所有運算子之前的函子和系結。</span><span class="sxs-lookup"><span data-stu-id="6dce7-357">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="6dce7-358">運算和函式呼叫的括弧也會系結在任何運算子之前，但是在陣列索引和函子之後。</span><span class="sxs-lookup"><span data-stu-id="6dce7-358">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="6dce7-359">依優先順序排列的運算子，從最高到最低：</span><span class="sxs-lookup"><span data-stu-id="6dce7-359">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="6dce7-360">運算子</span><span class="sxs-lookup"><span data-stu-id="6dce7-360">Operator</span></span> | <span data-ttu-id="6dce7-361">Arity</span><span class="sxs-lookup"><span data-stu-id="6dce7-361">Arity</span></span> | <span data-ttu-id="6dce7-362">描述</span><span class="sxs-lookup"><span data-stu-id="6dce7-362">Description</span></span> | <span data-ttu-id="6dce7-363">運算元類型</span><span class="sxs-lookup"><span data-stu-id="6dce7-363">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="6dce7-364">句號`!`</span><span class="sxs-lookup"><span data-stu-id="6dce7-364">trailing `!`</span></span> | <span data-ttu-id="6dce7-365">一元 (Unary)</span><span class="sxs-lookup"><span data-stu-id="6dce7-365">Unary</span></span> | <span data-ttu-id="6dce7-366">解除包裝</span><span class="sxs-lookup"><span data-stu-id="6dce7-366">Unwrap</span></span> | <span data-ttu-id="6dce7-367">任何使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="6dce7-367">Any user-defined type</span></span>
 <span data-ttu-id="6dce7-368">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="6dce7-368">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="6dce7-369">一元 (Unary)</span><span class="sxs-lookup"><span data-stu-id="6dce7-369">Unary</span></span> | <span data-ttu-id="6dce7-370">數值負數、位補數、邏輯否定</span><span class="sxs-lookup"><span data-stu-id="6dce7-370">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="6dce7-371">`Int`、 `BigInt` 或 `Double` 為 `-` ， `Int` 或 `BigInt` `~~~` 代表 `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="6dce7-371">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="6dce7-372">Binary</span><span class="sxs-lookup"><span data-stu-id="6dce7-372">Binary</span></span> | <span data-ttu-id="6dce7-373">整數乘冪</span><span class="sxs-lookup"><span data-stu-id="6dce7-373">Integer power</span></span> | <span data-ttu-id="6dce7-374">`Int`或 `BigInt` 作為基底， `Int` 代表指數</span><span class="sxs-lookup"><span data-stu-id="6dce7-374">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="6dce7-375">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="6dce7-375">`/`, `*`, `%`</span></span> | <span data-ttu-id="6dce7-376">Binary</span><span class="sxs-lookup"><span data-stu-id="6dce7-376">Binary</span></span> | <span data-ttu-id="6dce7-377">除法、乘法、integer 模數</span><span class="sxs-lookup"><span data-stu-id="6dce7-377">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="6dce7-378">`Int`、 `BigInt` 或 `Double` 適用于 `/` 和 `*` ， `Int` 或 `BigInt` 為`%`</span><span class="sxs-lookup"><span data-stu-id="6dce7-378">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="6dce7-379">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="6dce7-379">`+`, `-`</span></span> | <span data-ttu-id="6dce7-380">Binary</span><span class="sxs-lookup"><span data-stu-id="6dce7-380">Binary</span></span> | <span data-ttu-id="6dce7-381">加法或字串和陣列串連，減法</span><span class="sxs-lookup"><span data-stu-id="6dce7-381">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="6dce7-382">`Int`、 `BigInt` 或 `Double` ，此外 `String` 或任何的陣列類型`+`</span><span class="sxs-lookup"><span data-stu-id="6dce7-382">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="6dce7-383">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="6dce7-383">`<<<`, `>>>`</span></span> | <span data-ttu-id="6dce7-384">Binary</span><span class="sxs-lookup"><span data-stu-id="6dce7-384">Binary</span></span> | <span data-ttu-id="6dce7-385">左 shift、right shift</span><span class="sxs-lookup"><span data-stu-id="6dce7-385">Left shift, right shift</span></span> | <span data-ttu-id="6dce7-386">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6dce7-386">`Int` or `BigInt`</span></span>
 <span data-ttu-id="6dce7-387">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="6dce7-387">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="6dce7-388">Binary</span><span class="sxs-lookup"><span data-stu-id="6dce7-388">Binary</span></span> | <span data-ttu-id="6dce7-389">小於、小於或等於、大於、大於、等於或相等的比較</span><span class="sxs-lookup"><span data-stu-id="6dce7-389">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="6dce7-390">`Int`、 `BigInt` 或`Double`</span><span class="sxs-lookup"><span data-stu-id="6dce7-390">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="6dce7-391">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="6dce7-391">`==`, `!=`</span></span> | <span data-ttu-id="6dce7-392">Binary</span><span class="sxs-lookup"><span data-stu-id="6dce7-392">Binary</span></span> | <span data-ttu-id="6dce7-393">等於、不等於比較</span><span class="sxs-lookup"><span data-stu-id="6dce7-393">equal, not-equal comparisons</span></span> | <span data-ttu-id="6dce7-394">任何基本類型</span><span class="sxs-lookup"><span data-stu-id="6dce7-394">any primitive type</span></span>
 `&&&` | <span data-ttu-id="6dce7-395">Binary</span><span class="sxs-lookup"><span data-stu-id="6dce7-395">Binary</span></span> | <span data-ttu-id="6dce7-396">位元 AND</span><span class="sxs-lookup"><span data-stu-id="6dce7-396">Bitwise AND</span></span> | <span data-ttu-id="6dce7-397">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6dce7-397">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="6dce7-398">Binary</span><span class="sxs-lookup"><span data-stu-id="6dce7-398">Binary</span></span> | <span data-ttu-id="6dce7-399">位元 XOR</span><span class="sxs-lookup"><span data-stu-id="6dce7-399">Bitwise XOR</span></span> | <span data-ttu-id="6dce7-400">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6dce7-400">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="6dce7-401">Binary</span><span class="sxs-lookup"><span data-stu-id="6dce7-401">Binary</span></span> | <span data-ttu-id="6dce7-402">位元 OR</span><span class="sxs-lookup"><span data-stu-id="6dce7-402">Bitwise OR</span></span> | <span data-ttu-id="6dce7-403">`Int` 或 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6dce7-403">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="6dce7-404">Binary</span><span class="sxs-lookup"><span data-stu-id="6dce7-404">Binary</span></span> | <span data-ttu-id="6dce7-405">邏輯 AND</span><span class="sxs-lookup"><span data-stu-id="6dce7-405">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="6dce7-406">Binary</span><span class="sxs-lookup"><span data-stu-id="6dce7-406">Binary</span></span> | <span data-ttu-id="6dce7-407">邏輯 OR</span><span class="sxs-lookup"><span data-stu-id="6dce7-407">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="6dce7-408">Binary/三元</span><span class="sxs-lookup"><span data-stu-id="6dce7-408">Binary/Ternary</span></span> | <span data-ttu-id="6dce7-409">Range 運算子</span><span class="sxs-lookup"><span data-stu-id="6dce7-409">Range operator</span></span> | `Int`
 <span data-ttu-id="6dce7-410">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="6dce7-410">`?` `|`</span></span> | <span data-ttu-id="6dce7-411">三元</span><span class="sxs-lookup"><span data-stu-id="6dce7-411">Ternary</span></span> | <span data-ttu-id="6dce7-412">條件式</span><span class="sxs-lookup"><span data-stu-id="6dce7-412">Conditional</span></span> | <span data-ttu-id="6dce7-413">`Bool`左側的</span><span class="sxs-lookup"><span data-stu-id="6dce7-413">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="6dce7-414">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="6dce7-414">`w/` `<-`</span></span> | <span data-ttu-id="6dce7-415">三元</span><span class="sxs-lookup"><span data-stu-id="6dce7-415">Ternary</span></span> | <span data-ttu-id="6dce7-416">複製和更新</span><span class="sxs-lookup"><span data-stu-id="6dce7-416">Copy-and-update</span></span> | <span data-ttu-id="6dce7-417">請參閱[複製和更新運算式](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="6dce7-417">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="6dce7-418">後續步驟</span><span class="sxs-lookup"><span data-stu-id="6dce7-418">Next steps</span></span>

<span data-ttu-id="6dce7-419">現在您可以使用 Q # 中的運算式，您可以前往[q # 中的作業和](xref:microsoft.quantum.guide.operationsfunctions)函式，以瞭解如何定義和呼叫作業和函數。</span><span class="sxs-lookup"><span data-stu-id="6dce7-419">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
