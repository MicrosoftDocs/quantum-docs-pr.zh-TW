---
title: 'Q # 語句 |Microsoft Docs'
description: 'Q # 語句'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5bcbee868c76aaf53d0b7969e6e634da62689aaa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184860"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="cb576-103">語句和其他結構</span><span class="sxs-lookup"><span data-stu-id="cb576-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="cb576-104">註解</span><span class="sxs-lookup"><span data-stu-id="cb576-104">Comments</span></span>

<span data-ttu-id="cb576-105">批註的開頭為兩個正斜線，`//`，並繼續直到行尾為止。</span><span class="sxs-lookup"><span data-stu-id="cb576-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="cb576-106">批註可能會出現在 Q # 來源檔案中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="cb576-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="cb576-107">檔批註</span><span class="sxs-lookup"><span data-stu-id="cb576-107">Documentation Comments</span></span>

<span data-ttu-id="cb576-108">當編譯器在命名空間、作業、特製化、函式或類型定義之前出現時，會以特殊方式處理開頭為三個正斜線（`///`）的批註。</span><span class="sxs-lookup"><span data-stu-id="cb576-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="cb576-109">在此情況下，會將其內容視為已定義之可呼叫或使用者定義類型的檔，就像其他 .NET 語言一樣。</span><span class="sxs-lookup"><span data-stu-id="cb576-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="cb576-110">在 `///` 批註中，顯示為 API 檔一部分的文字會格式化為[Markdown](https://daringfireball.net/projects/markdown/syntax)，並以特殊命名的標頭指出檔的不同部分。</span><span class="sxs-lookup"><span data-stu-id="cb576-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="cb576-111">如需 Markdown 的延伸模組，可以使用 `@"<ref target>"`包含 Q # 中作業、函式和使用者定義類型的交互參考，其中 `<ref target>` 會由所參考之程式碼物件的完整名稱取代。</span><span class="sxs-lookup"><span data-stu-id="cb576-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="cb576-112">（選擇性）檔引擎也可能支援其他 Markdown 延伸模組。</span><span class="sxs-lookup"><span data-stu-id="cb576-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="cb576-113">例如：</span><span class="sxs-lookup"><span data-stu-id="cb576-113">For example:</span></span>

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit
{
    op(target);
    op(target);
}
```

<span data-ttu-id="cb576-114">下列名稱會被辨識為檔批註標頭。</span><span class="sxs-lookup"><span data-stu-id="cb576-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="cb576-115">**摘要**：函數或作業行為的簡短摘要，或類型的用途。</span><span class="sxs-lookup"><span data-stu-id="cb576-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="cb576-116">摘要的第一個段落用於暫留資訊。</span><span class="sxs-lookup"><span data-stu-id="cb576-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="cb576-117">它應該是純文字。</span><span class="sxs-lookup"><span data-stu-id="cb576-117">It should be plain text.</span></span>
- <span data-ttu-id="cb576-118">**描述**：函數或作業行為的描述，或類型的用途說明。</span><span class="sxs-lookup"><span data-stu-id="cb576-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="cb576-119">摘要和描述會串連，以形成函式、作業或類型所產生的檔檔案。</span><span class="sxs-lookup"><span data-stu-id="cb576-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="cb576-120">描述可以包含內嵌 LaTeX 格式的符號和方程式。</span><span class="sxs-lookup"><span data-stu-id="cb576-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="cb576-121">**輸入**：作業或函數之輸入元組的描述。</span><span class="sxs-lookup"><span data-stu-id="cb576-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="cb576-122">可能包含其他 Markdown 子區段，指示輸入元組的每個個別元素。</span><span class="sxs-lookup"><span data-stu-id="cb576-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="cb576-123">**輸出**：作業或函式所傳回之元組的描述。</span><span class="sxs-lookup"><span data-stu-id="cb576-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="cb576-124">**型別參數**：空的區段，其中包含每個泛型型別參數的一個額外子節。</span><span class="sxs-lookup"><span data-stu-id="cb576-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="cb576-125">**範例**：使用中的作業、函數或類型的簡短範例。</span><span class="sxs-lookup"><span data-stu-id="cb576-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="cb576-126">**備註**：其他 prose，描述作業、函數或類型的某些層面。</span><span class="sxs-lookup"><span data-stu-id="cb576-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="cb576-127">**另請參閱**：表示相關函數、作業或使用者定義類型的完整名稱清單。</span><span class="sxs-lookup"><span data-stu-id="cb576-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="cb576-128">**參考**：要記載之專案的參考和引文清單。</span><span class="sxs-lookup"><span data-stu-id="cb576-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="cb576-129">命名空間</span><span class="sxs-lookup"><span data-stu-id="cb576-129">Namespaces</span></span>

<span data-ttu-id="cb576-130">每個 Q # 作業、函式和使用者定義類型都定義在命名空間中。</span><span class="sxs-lookup"><span data-stu-id="cb576-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="cb576-131">問 # 遵循與其他 .NET 語言相同的命名規則。</span><span class="sxs-lookup"><span data-stu-id="cb576-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="cb576-132">不過，Q # 不支援命名空間的相對參考。</span><span class="sxs-lookup"><span data-stu-id="cb576-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="cb576-133">也就是說，如果已開啟命名空間 `a.b`，`c.d` 的作業名稱參考將不會解析為完整名稱 `a.b.c.d`的作業。</span><span class="sxs-lookup"><span data-stu-id="cb576-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="cb576-134">在命名空間區塊內，`open` 指示詞可用來匯入特定命名空間中宣告的所有類型和 callables，並依其不合格的名稱加以參考。</span><span class="sxs-lookup"><span data-stu-id="cb576-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="cb576-135">（選擇性）可能會定義已開啟之命名空間的簡短名稱，讓來自該命名空間的所有元素都可以（和需要）以定義的簡短名稱限定。</span><span class="sxs-lookup"><span data-stu-id="cb576-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="cb576-136">`open` 指示詞適用于檔案內的整個命名空間區塊。</span><span class="sxs-lookup"><span data-stu-id="cb576-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="cb576-137">在未于目前命名空間中開啟的另一個命名空間中定義的類型或可呼叫，必須以其完整名稱來參考。</span><span class="sxs-lookup"><span data-stu-id="cb576-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="cb576-138">例如，除非先前已在目前區塊中開啟 `X.Y` 命名空間，否則 `X.Y` 命名空間中名為 `Op` 的作業必須由其完整名稱 `X.Y.Op`參考。</span><span class="sxs-lookup"><span data-stu-id="cb576-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="cb576-139">如上所述，即使已開啟 `X` 的命名空間，也無法以 `Y.Op`的方式來參考作業。</span><span class="sxs-lookup"><span data-stu-id="cb576-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="cb576-140">如果已在該命名空間和檔案中定義 `X.Y` 的簡短名稱 `Z`，則 `Op` 必須稱為 `Z.Op`。</span><span class="sxs-lookup"><span data-stu-id="cb576-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {

    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="cb576-141">通常最好是使用 `open` 指示詞來加入命名空間。</span><span class="sxs-lookup"><span data-stu-id="cb576-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="cb576-142">如果兩個命名空間定義具有相同名稱的結構，而且目前來源使用兩者的結構，則必須使用完整名稱。</span><span class="sxs-lookup"><span data-stu-id="cb576-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="cb576-143">格式化</span><span class="sxs-lookup"><span data-stu-id="cb576-143">Formatting</span></span>

<span data-ttu-id="cb576-144">大部分的 Q # 語句和指示詞的結尾都是終止的分號，`;`。</span><span class="sxs-lookup"><span data-stu-id="cb576-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="cb576-145">語句和宣告（例如 `for` 和 `operation` 以語句區塊結尾）不需要終止分號。</span><span class="sxs-lookup"><span data-stu-id="cb576-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="cb576-146">每個語句描述都會說明結尾分號是否為必要。</span><span class="sxs-lookup"><span data-stu-id="cb576-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="cb576-147">語句（例如運算式、宣告和指示詞）可能會細分成多行。</span><span class="sxs-lookup"><span data-stu-id="cb576-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="cb576-148">應避免在單一行上使用多個語句。</span><span class="sxs-lookup"><span data-stu-id="cb576-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="cb576-149">語句區塊</span><span class="sxs-lookup"><span data-stu-id="cb576-149">Statement Blocks</span></span>

<span data-ttu-id="cb576-150">Q # 語句會分組到語句區塊中。</span><span class="sxs-lookup"><span data-stu-id="cb576-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="cb576-151">語句區塊會以開啟的 `{` 開頭，並以結尾 `}`結束。</span><span class="sxs-lookup"><span data-stu-id="cb576-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="cb576-152">在另一個區塊中以詞法括住的語句區塊，會被視為包含區塊的子區塊;包含和子區塊也稱為外部和內部區塊。</span><span class="sxs-lookup"><span data-stu-id="cb576-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="cb576-153">符號系結和指派</span><span class="sxs-lookup"><span data-stu-id="cb576-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="cb576-154">Q # 區分可變和不可變的符號。</span><span class="sxs-lookup"><span data-stu-id="cb576-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="cb576-155">一般來說，我們鼓勵使用不可變的符號，因為它可讓編譯器執行更多的優化。</span><span class="sxs-lookup"><span data-stu-id="cb576-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="cb576-156">系結的左邊是由符號元組和運算式的右手邊所組成。</span><span class="sxs-lookup"><span data-stu-id="cb576-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="cb576-157">由於所有 Q # 類型都是實值型別-qubits 採用有點特殊的角色，因此，當值系結至符號或符號重新系結時，就會建立「複製」。</span><span class="sxs-lookup"><span data-stu-id="cb576-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="cb576-158">也就是說，問 # 的行為與在指派時建立複本相同。</span><span class="sxs-lookup"><span data-stu-id="cb576-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="cb576-159">這也特別包括陣列。</span><span class="sxs-lookup"><span data-stu-id="cb576-159">This in particular also includes arrays.</span></span> <span data-ttu-id="cb576-160">當然，實際上只有相關的部分會在需要時重新建立。</span><span class="sxs-lookup"><span data-stu-id="cb576-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="cb576-161">元組解構</span><span class="sxs-lookup"><span data-stu-id="cb576-161">Tuple Deconstruction</span></span>

<span data-ttu-id="cb576-162">如果系結的右手邊是元組，則該元組在指派時可能會解構。</span><span class="sxs-lookup"><span data-stu-id="cb576-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="cb576-163">這類解構可能牽涉到嵌套的元組，只要右側元組的形狀與符號元組的形狀相容，任何完整或部分解構都是有效的。</span><span class="sxs-lookup"><span data-stu-id="cb576-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="cb576-164">當 `=` 的右手邊為元組值運算式時，也可以特別使用元組解構。</span><span class="sxs-lookup"><span data-stu-id="cb576-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="cb576-165">不可變的符號</span><span class="sxs-lookup"><span data-stu-id="cb576-165">Immutable Symbols</span></span>

<span data-ttu-id="cb576-166">不可變的符號會使用 `let` 語句來系結。</span><span class="sxs-lookup"><span data-stu-id="cb576-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="cb576-167">這大致等同于中的變數宣告和初始化（例如C#），不同之處在于問 # 符號在系結之後可能不會變更;`let` 系結是不可變的。</span><span class="sxs-lookup"><span data-stu-id="cb576-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="cb576-168">不可變的系結包含關鍵字 `let`，後面接著符號或符號元組、等號 `=`、用來系結符號的運算式，以及終止的分號。</span><span class="sxs-lookup"><span data-stu-id="cb576-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="cb576-169">系結符號的類型是根據右手邊的運算式來推斷。</span><span class="sxs-lookup"><span data-stu-id="cb576-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="cb576-170">可變符號</span><span class="sxs-lookup"><span data-stu-id="cb576-170">Mutable Symbols</span></span>

<span data-ttu-id="cb576-171">可變動的符號會使用 `mutable` 語句來定義和初始化。</span><span class="sxs-lookup"><span data-stu-id="cb576-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="cb576-172">宣告和系結為 `mutable` 語句之一部分的符號，在稍後的程式碼中可能會重新系結至不同的值。</span><span class="sxs-lookup"><span data-stu-id="cb576-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="cb576-173">可變動的系結語句包含關鍵字 `mutable`，後面接著符號或符號元組、等號 `=`、用來系結符號的運算式，以及終止的分號。</span><span class="sxs-lookup"><span data-stu-id="cb576-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="cb576-174">系結符號的類型是根據右手邊的運算式來推斷。</span><span class="sxs-lookup"><span data-stu-id="cb576-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="cb576-175">如果稍後在程式碼中重新系結符號，它的類型不會變更，而且系結的值必須與該類型相容。</span><span class="sxs-lookup"><span data-stu-id="cb576-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="cb576-176">可變動符號的重新系結</span><span class="sxs-lookup"><span data-stu-id="cb576-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="cb576-177">可變動的變數可能會使用 `set` 語句來重新系結。</span><span class="sxs-lookup"><span data-stu-id="cb576-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="cb576-178">這類重新系結包含關鍵字 `set`，後面接著符號或符號元組、等號 `=`、將符號重新系結至的運算式，以及終止的分號。</span><span class="sxs-lookup"><span data-stu-id="cb576-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="cb576-179">此值必須與所系結之符號的類型相容。</span><span class="sxs-lookup"><span data-stu-id="cb576-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="cb576-180">Apply-重新指派語句</span><span class="sxs-lookup"><span data-stu-id="cb576-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="cb576-181">我們稱為 apply 和-重新指派語句的一種特殊類型的集合語句，會在右側包含二元運算子的應用程式，並將結果重新系結至運算子的左邊引數時，提供便利的串連方式。</span><span class="sxs-lookup"><span data-stu-id="cb576-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="cb576-182">例如，</span><span class="sxs-lookup"><span data-stu-id="cb576-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="cb576-183">在 `for` 迴圈的每個反復專案中，遞增計數器 `counter` 的值。</span><span class="sxs-lookup"><span data-stu-id="cb576-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="cb576-184">上述程式碼相當於</span><span class="sxs-lookup"><span data-stu-id="cb576-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="cb576-185">所有二元運算子都有類似的語句，其中左邊的型別符合運算式型別。</span><span class="sxs-lookup"><span data-stu-id="cb576-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="cb576-186">這會提供一個簡單的方法來累積值：</span><span class="sxs-lookup"><span data-stu-id="cb576-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (q in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="cb576-187">Update-重新指派語句</span><span class="sxs-lookup"><span data-stu-id="cb576-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="cb576-188">右手邊的複製和更新運算式會有類似的串連。</span><span class="sxs-lookup"><span data-stu-id="cb576-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="cb576-189">同樣地，使用者定義型別中的命名專案以及陣列專案的更新和重新指派語句也會存在。</span><span class="sxs-lookup"><span data-stu-id="cb576-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function AddAll (reals : Double[], ims : Double[]) : Complex[] {
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

<span data-ttu-id="cb576-190">在陣列的案例中，我們的標準程式庫包含許多常見陣列初始化和操作需求所需的工具，因此可協助避免必須在一開始就更新陣列專案。</span><span class="sxs-lookup"><span data-stu-id="cb576-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="cb576-191">Update-重新指派語句會在需要時提供替代方法：</span><span class="sxs-lookup"><span data-stu-id="cb576-191">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {

    mutable samples = new Double[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}

operation SampleUniformDistr(nrSamples : Int, prec : Int) : Double[] {

    let normalization = 1. / IntAsDouble(prec);
    mutable samples = RandomInts(prec, nrSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> <span data-ttu-id="cb576-192">利用 <xref:microsoft.quantum.arrays>中提供的工具，避免不必要地使用 update 和重新指派語句。</span><span class="sxs-lookup"><span data-stu-id="cb576-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="cb576-193">函式</span><span class="sxs-lookup"><span data-stu-id="cb576-193">The function</span></span>
```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
{
    mutable pauliArray = new Pauli[n];
    for (index in 0 .. n - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
<span data-ttu-id="cb576-194">例如，您可以使用 `Microsoft.Quantum.Arrays`中的函式 `ConstantArray` 來簡化，並傳回復制和更新運算式：</span><span class="sxs-lookup"><span data-stu-id="cb576-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    return ConstantArray(n, PauliI) w/ i <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="cb576-195">系結範圍</span><span class="sxs-lookup"><span data-stu-id="cb576-195">Binding Scopes</span></span>

<span data-ttu-id="cb576-196">一般而言，符號系結會超出範圍，而且會在其發生的語句區塊結尾處變成無法執行。</span><span class="sxs-lookup"><span data-stu-id="cb576-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="cb576-197">此規則有兩個例外狀況：</span><span class="sxs-lookup"><span data-stu-id="cb576-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="cb576-198">`for` 迴圈之迴圈變數的系結是在 for 迴圈主體的範圍內，而不是在迴圈結束之後。</span><span class="sxs-lookup"><span data-stu-id="cb576-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="cb576-199">`repeat`/`until` 迴圈（主體、測試和修復）的三個部分會視為單一範圍，因此在本文中系結的符號會在測試和修復中提供。</span><span class="sxs-lookup"><span data-stu-id="cb576-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="cb576-200">對於這兩種類型的迴圈，每次通過迴圈都會在其本身的範圍中執行，因此在稍後的階段中，不會提供來自較早階段的系結。</span><span class="sxs-lookup"><span data-stu-id="cb576-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="cb576-201">內部區塊會繼承外部區塊的符號系結。</span><span class="sxs-lookup"><span data-stu-id="cb576-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="cb576-202">符號只能系結每個區塊一次;定義符號的名稱與範圍內的另一個符號（不是「遮蔽」）並不合法。</span><span class="sxs-lookup"><span data-stu-id="cb576-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="cb576-203">下列順序會是合法的：</span><span class="sxs-lookup"><span data-stu-id="cb576-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="cb576-204">與</span><span class="sxs-lookup"><span data-stu-id="cb576-204">and</span></span>

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
```

<span data-ttu-id="cb576-205">但這不合法：</span><span class="sxs-lookup"><span data-stu-id="cb576-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="cb576-206">如下所示：</span><span class="sxs-lookup"><span data-stu-id="cb576-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="cb576-207">控制流程</span><span class="sxs-lookup"><span data-stu-id="cb576-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="cb576-208">For 迴圈</span><span class="sxs-lookup"><span data-stu-id="cb576-208">For Loop</span></span>

<span data-ttu-id="cb576-209">`for` 語句支援整數範圍或陣列上的反復專案。</span><span class="sxs-lookup"><span data-stu-id="cb576-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="cb576-210">語句包含關鍵字 `for`、左括弧 `(`，後面接著符號或符號元組、關鍵字 `in`、`Range` 或陣列類型的運算式、右括弧 `)`和語句區塊。</span><span class="sxs-lookup"><span data-stu-id="cb576-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="cb576-211">語句區塊（迴圈的主體）會重複執行，其中已定義的符號（迴圈變數）會系結至範圍或陣列中的每個值。</span><span class="sxs-lookup"><span data-stu-id="cb576-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="cb576-212">請注意，如果範圍運算式評估為空的範圍或陣列，則完全不會執行主體。</span><span class="sxs-lookup"><span data-stu-id="cb576-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="cb576-213">在進入迴圈之前，會完整評估運算式，而且在執行迴圈時不會變更。</span><span class="sxs-lookup"><span data-stu-id="cb576-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="cb576-214">宣告之符號的系結是不可變的，並遵循與其他變數系結相同的規則。</span><span class="sxs-lookup"><span data-stu-id="cb576-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="cb576-215">特別的是，在指派給迴圈變數時，可能會在陣列上進行反覆運算的陣列專案（例如）。</span><span class="sxs-lookup"><span data-stu-id="cb576-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="cb576-216">例如，</span><span class="sxs-lookup"><span data-stu-id="cb576-216">For example,</span></span>

```qsharp
// ...
for (qb in qubits) { // qubits contains a Qubit[]
    H(qb);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="cb576-217">迴圈變數會系結至迴圈主體的每個進入，並在主體結尾處解除系結。</span><span class="sxs-lookup"><span data-stu-id="cb576-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="cb576-218">特別是，在 for 迴圈完成之後，迴圈變數不會系結。</span><span class="sxs-lookup"><span data-stu-id="cb576-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="cb576-219">重複直到-成功迴圈</span><span class="sxs-lookup"><span data-stu-id="cb576-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="cb576-220">`repeat` 語句支援「重複直到成功」模式的量子。</span><span class="sxs-lookup"><span data-stu-id="cb576-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="cb576-221">其中包含關鍵字 `repeat`，後面接著語句區塊（_迴圈_主體）、關鍵字 `until`、布林運算式，以及結尾的分號或關鍵字 `fixup` 後面接著另一個語句區塊（_修復_）。</span><span class="sxs-lookup"><span data-stu-id="cb576-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="cb576-222">「迴圈主體」、「條件」和「修復」全都視為單一範圍，因此本文中系結的符號會出現在條件和修復中。</span><span class="sxs-lookup"><span data-stu-id="cb576-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qs);
    let success = ComputeSuccessIndicator(qs);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qs);
}
```

<span data-ttu-id="cb576-223">執行迴圈主體，然後評估條件。</span><span class="sxs-lookup"><span data-stu-id="cb576-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="cb576-224">如果條件為 true，則表示語句已完成;否則，會執行修復，並從迴圈主體開始重新執行語句。</span><span class="sxs-lookup"><span data-stu-id="cb576-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="cb576-225">請注意，完成修復的執行會結束語句的範圍，因此在本文或修復期間所做的符號系結，無法用於後續的重複。</span><span class="sxs-lookup"><span data-stu-id="cb576-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="cb576-226">例如，下列程式碼是使用 Hadamard 和 T 閘道 $V _3 = （\boldone + 2 i Z）/\sqrt{5}$ 執行重要旋轉閘道的概率電路。</span><span class="sxs-lookup"><span data-stu-id="cb576-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="cb576-227">迴圈會平均終止8/5 重複。</span><span class="sxs-lookup"><span data-stu-id="cb576-227">The loop terminates in 8/5 repetitions on average.</span></span>
<span data-ttu-id="cb576-228">如需詳細資訊，請參閱[*重複直到成功：單一 qubit unitaries 的非決定性分解*](https://arxiv.org/abs/1311.1074)（Paetznick 和 Svore，2014）。</span><span class="sxs-lookup"><span data-stu-id="cb576-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

```qsharp
using (anc = Qubit()) {
    repeat {
        H(anc);
        T(anc);
        CNOT(target,anc);
        H(anc);
        Adjoint T(anc);
        H(anc);
        T(anc);
        H(anc);
        CNOT(target,anc);
        T(anc);
        Z(target);
        H(anc);
        let result = M(anc);
    } until (result == Zero);
}
```

> [!TIP]   
> <span data-ttu-id="cb576-229">避免在函式內使用重複-成功迴圈。</span><span class="sxs-lookup"><span data-stu-id="cb576-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="cb576-230">對應的功能是由函式中的迴圈所提供。</span><span class="sxs-lookup"><span data-stu-id="cb576-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="cb576-231">While 迴圈</span><span class="sxs-lookup"><span data-stu-id="cb576-231">While Loop</span></span>

<span data-ttu-id="cb576-232">重複直到-成功模式具有非常量子特定的含意。</span><span class="sxs-lookup"><span data-stu-id="cb576-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="cb576-233">它們廣泛用於特定的量子演算法類別中，因此是 Q # 中的專用語言結構。</span><span class="sxs-lookup"><span data-stu-id="cb576-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="cb576-234">不過，根據條件中斷的迴圈，在編譯時期，其執行長度會是未知的，需要在量子執行時間中特別小心處理。</span><span class="sxs-lookup"><span data-stu-id="cb576-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="cb576-235">另一方面，它們在函式中的用法是 unproblematic，因為這些只包含將在傳統（非量子）硬體上執行的程式碼。</span><span class="sxs-lookup"><span data-stu-id="cb576-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="cb576-236">問 # 因此僅支援在函式內使用 while 迴圈。</span><span class="sxs-lookup"><span data-stu-id="cb576-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="cb576-237">`while` 語句包含關鍵字 `while`、左括弧 `(`、條件（例如布林運算式）、右括弧 `)`和語句區塊。</span><span class="sxs-lookup"><span data-stu-id="cb576-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="cb576-238">只要條件評估為 `true`，就會執行語句區塊（迴圈的主體）。</span><span class="sxs-lookup"><span data-stu-id="cb576-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="cb576-239">條件陳述式</span><span class="sxs-lookup"><span data-stu-id="cb576-239">Conditional Statement</span></span>

<span data-ttu-id="cb576-240">`if` 語句支援條件式執行。</span><span class="sxs-lookup"><span data-stu-id="cb576-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="cb576-241">其中包含關鍵字 `if`、左括弧 `(`、布林運算式、右括弧 `)`，以及語句區塊（ _then_區塊）。</span><span class="sxs-lookup"><span data-stu-id="cb576-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="cb576-242">後面可能會接著任意數目的 else if 子句，其中每個都包含關鍵字 `elif`、左括弧 `(`、布林運算式、右括弧 `)`和語句區塊（ _else-if_區塊）。</span><span class="sxs-lookup"><span data-stu-id="cb576-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="cb576-243">最後，語句可能會選擇性地以 else 子句完成，其中包含關鍵字 `else` 後面接著另一個語句區塊（ _else_區塊）。</span><span class="sxs-lookup"><span data-stu-id="cb576-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="cb576-244">條件會進行評估，如果為 true，則會執行 then 區塊。</span><span class="sxs-lookup"><span data-stu-id="cb576-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="cb576-245">如果條件為 false，則會評估第一個 else if 條件;如果是 true，則為，否則為。</span><span class="sxs-lookup"><span data-stu-id="cb576-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="cb576-246">否則，會先測試第二個 [if] 區塊，然後再進行第三個，直到出現具有 true 條件的子句，或沒有其他的 if 子句為止。</span><span class="sxs-lookup"><span data-stu-id="cb576-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="cb576-247">如果原始 if 條件和所有 else if 子句評估為 false，則會執行 else 區塊（如果有提供的話）。</span><span class="sxs-lookup"><span data-stu-id="cb576-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="cb576-248">請注意，執行的任何區塊會在其本身的範圍中執行。</span><span class="sxs-lookup"><span data-stu-id="cb576-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="cb576-249">在 if 語句結尾之後，不會顯示在 then、if、或 else 區塊內進行的系結。</span><span class="sxs-lookup"><span data-stu-id="cb576-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="cb576-250">例如，</span><span class="sxs-lookup"><span data-stu-id="cb576-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="cb576-251">或</span><span class="sxs-lookup"><span data-stu-id="cb576-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="cb576-252">傳回</span><span class="sxs-lookup"><span data-stu-id="cb576-252">Return</span></span>

<span data-ttu-id="cb576-253">Return 語句會結束執行作業或函數，並將值傳回給呼叫者。</span><span class="sxs-lookup"><span data-stu-id="cb576-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="cb576-254">其中包含關鍵字 `return`，後面接著適當類型的運算式和結束分號。</span><span class="sxs-lookup"><span data-stu-id="cb576-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="cb576-255">可呼叫會傳回空的元組，`()`，不需要 return 語句。</span><span class="sxs-lookup"><span data-stu-id="cb576-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="cb576-256">如果需要提早結束，在此情況下，可能會用到 `return ()`。</span><span class="sxs-lookup"><span data-stu-id="cb576-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="cb576-257">傳回任何其他類型的 Callables 都需要最終傳回語句。</span><span class="sxs-lookup"><span data-stu-id="cb576-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="cb576-258">作業中沒有 return 語句的最大數目。</span><span class="sxs-lookup"><span data-stu-id="cb576-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="cb576-259">如果語句在區塊內遵循 return 語句，則編譯器可能會發出警告。</span><span class="sxs-lookup"><span data-stu-id="cb576-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="cb576-260">例如，</span><span class="sxs-lookup"><span data-stu-id="cb576-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="cb576-261">或</span><span class="sxs-lookup"><span data-stu-id="cb576-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="cb576-262">或</span><span class="sxs-lookup"><span data-stu-id="cb576-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="cb576-263">不合格</span><span class="sxs-lookup"><span data-stu-id="cb576-263">Fail</span></span>

<span data-ttu-id="cb576-264">Fail 語句會結束執行作業，並將錯誤值傳回給呼叫者。</span><span class="sxs-lookup"><span data-stu-id="cb576-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="cb576-265">其中包含關鍵字 `fail`，後面接著字串和結尾的分號。</span><span class="sxs-lookup"><span data-stu-id="cb576-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="cb576-266">字串會傳回給傳統驅動程式，做為錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="cb576-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="cb576-267">作業內的 fail 語句數目沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="cb576-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="cb576-268">如果語句在區塊內遵循 fail 語句，則編譯器可能會發出警告。</span><span class="sxs-lookup"><span data-stu-id="cb576-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="cb576-269">例如，</span><span class="sxs-lookup"><span data-stu-id="cb576-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="cb576-270">或</span><span class="sxs-lookup"><span data-stu-id="cb576-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="cb576-271">Qubit 管理</span><span class="sxs-lookup"><span data-stu-id="cb576-271">Qubit Management</span></span>

<span data-ttu-id="cb576-272">請注意，函式的主體中不允許任何這些語句。</span><span class="sxs-lookup"><span data-stu-id="cb576-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="cb576-273">只有在作業內才有效。</span><span class="sxs-lookup"><span data-stu-id="cb576-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="cb576-274">清除 Qubits</span><span class="sxs-lookup"><span data-stu-id="cb576-274">Clean Qubits</span></span>

<span data-ttu-id="cb576-275">`using` 語句是用來取得語句區塊期間使用的新 qubits。</span><span class="sxs-lookup"><span data-stu-id="cb576-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="cb576-276">Qubits 保證會初始化為計算 `Zero` 狀態。</span><span class="sxs-lookup"><span data-stu-id="cb576-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="cb576-277">Qubits 應該位於語句區塊結尾的計算 `Zero` 狀態;建議使用模擬器來強制執行。</span><span class="sxs-lookup"><span data-stu-id="cb576-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="cb576-278">語句包含關鍵字 `using`，後面接著左括弧 `(`、系結、右括弧 `)`，以及可使用 qubits 的語句區塊。</span><span class="sxs-lookup"><span data-stu-id="cb576-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="cb576-279">系結遵循與 `let` 語句相同的模式：單一符號或符號的元組，後面接著等號 `=`，以及單一值或相符的初始化運算式元組。</span><span class="sxs-lookup"><span data-stu-id="cb576-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="cb576-280">初始化運算式適用于單一 qubit，表示為 `Qubit()`或 qubits 陣列，以 `Qubit[`、`Int` 運算式和 `]`表示。</span><span class="sxs-lookup"><span data-stu-id="cb576-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="cb576-281">例如，</span><span class="sxs-lookup"><span data-stu-id="cb576-281">For example,</span></span>

```qsharp
using (q = Qubit()) {
    // ...
}
using ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="dirty-qubits"></a><span data-ttu-id="cb576-282">已變更 Qubits</span><span class="sxs-lookup"><span data-stu-id="cb576-282">Dirty Qubits</span></span>

<span data-ttu-id="cb576-283">`borrowing` 語句是用來取得暫時使用的 qubits。</span><span class="sxs-lookup"><span data-stu-id="cb576-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="cb576-284">語句包含關鍵字 `borrowing`，後面接著左括弧 `(`、系結、右括弧 `)`，以及可使用 qubits 的語句區塊。</span><span class="sxs-lookup"><span data-stu-id="cb576-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="cb576-285">系結會遵循與 `using` 語句中的相同模式和規則。</span><span class="sxs-lookup"><span data-stu-id="cb576-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="cb576-286">例如，</span><span class="sxs-lookup"><span data-stu-id="cb576-286">For example,</span></span>

```qsharp
borrowing (q = Qubit()) {
    // ...
}
borrowing ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="cb576-287">借用的 qubits 處於不明狀態，超出語句區塊結尾的範圍。</span><span class="sxs-lookup"><span data-stu-id="cb576-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="cb576-288">借方會認可，使 qubits 處於借用時的相同狀態，也就是其在語句區塊開頭和結尾的狀態應該是相同的。</span><span class="sxs-lookup"><span data-stu-id="cb576-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="cb576-289">此狀態特別不一定是傳統狀態，因此在大部分情況下，借用範圍不應包含測量。</span><span class="sxs-lookup"><span data-stu-id="cb576-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="cb576-290">這種 qubits 通常稱為「中途 ancilla」。</span><span class="sxs-lookup"><span data-stu-id="cb576-290">Such qubits are often known as “dirty ancilla”.</span></span>
<span data-ttu-id="cb576-291">如需已中途 Svore 使用的範例，請參閱[*使用具有以 Toffoli 為基礎的模組化乘法*](https://arxiv.org/abs/1611.07995)（Haner、Roetteler 和 ancilla 2017）的 2n + 2 qubits 進行的分解。</span><span class="sxs-lookup"><span data-stu-id="cb576-291">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of dirty ancilla use.</span></span>

<span data-ttu-id="cb576-292">當借用 qubits 時，系統會先嘗試從使用中的 qubits 填入要求，但在 `borrowing` 語句的本文中不會存取。</span><span class="sxs-lookup"><span data-stu-id="cb576-292">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="cb576-293">如果沒有足夠的 qubits，則會配置新的 qubits 來完成要求。</span><span class="sxs-lookup"><span data-stu-id="cb576-293">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="cb576-294">動詞變化</span><span class="sxs-lookup"><span data-stu-id="cb576-294">Conjugations</span></span>

<span data-ttu-id="cb576-295">相較于傳統的位，釋出配量記憶體會稍微複雜一點，因為如果 qubits 仍光子，則盲目重設 qubits 可能會對其餘的計算造成不想要的效果。</span><span class="sxs-lookup"><span data-stu-id="cb576-295">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="cb576-296">在釋放記憶體之前，適當地「復原」執行的計算，可以避免這種情況。</span><span class="sxs-lookup"><span data-stu-id="cb576-296">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="cb576-297">量子運算的常見模式如下：</span><span class="sxs-lookup"><span data-stu-id="cb576-297">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="cb576-298">：新的：從0.9 版開始，我們支援 conjugation 語句來執行上述轉換。</span><span class="sxs-lookup"><span data-stu-id="cb576-298">:new: Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="cb576-299">使用該語句，可以透過下列方式來執行作業 `ApplyWith`：</span><span class="sxs-lookup"><span data-stu-id="cb576-299">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="cb576-300">如果外部和內部轉換無法立即當做作業使用，這類 conjugation 語句會變得更有用，但以多個語句所組成的區塊來描述會更方便。</span><span class="sxs-lookup"><span data-stu-id="cb576-300">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="cb576-301">在區塊內定義的語句的反向轉換會由編譯器自動產生，並在套用區塊完成後執行。</span><span class="sxs-lookup"><span data-stu-id="cb576-301">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="cb576-302">因為任何用來做為內部區塊一部分的可變變數無法在套用區塊中重新系結，所以產生的轉換保證會是在區塊內的計算 adjoint。</span><span class="sxs-lookup"><span data-stu-id="cb576-302">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="cb576-303">運算式評估語句</span><span class="sxs-lookup"><span data-stu-id="cb576-303">Expression Evaluation Statements</span></span>

<span data-ttu-id="cb576-304">`Unit` 類型的任何呼叫運算式可以當做語句使用。</span><span class="sxs-lookup"><span data-stu-id="cb576-304">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="cb576-305">這主要是在對傳回 `Unit` 的 qubits 呼叫作業時使用，因為語句的目的是要修改隱含的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="cb576-305">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="cb576-306">運算式評估語句需要結尾的分號。</span><span class="sxs-lookup"><span data-stu-id="cb576-306">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="cb576-307">例如，</span><span class="sxs-lookup"><span data-stu-id="cb576-307">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
