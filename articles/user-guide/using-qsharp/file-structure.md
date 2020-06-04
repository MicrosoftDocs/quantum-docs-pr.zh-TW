---
title: 'Q # 檔案結構'
description: '說明 Q # 檔案的結構和語法。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327453"
---
# <a name="q-file-structure"></a><span data-ttu-id="a03a6-103">Q # 檔案結構</span><span class="sxs-lookup"><span data-stu-id="a03a6-103">Q# File Structure</span></span>

<span data-ttu-id="a03a6-104">每個 Q # 作業、函式和使用者定義類型都定義在命名空間中。</span><span class="sxs-lookup"><span data-stu-id="a03a6-104">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>

<span data-ttu-id="a03a6-105">Q # 檔案是由一系列的*命名空間*宣告所組成。</span><span class="sxs-lookup"><span data-stu-id="a03a6-105">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="a03a6-106">每個命名空間宣告都包含使用者定義類型、作業和函式的宣告。</span><span class="sxs-lookup"><span data-stu-id="a03a6-106">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="a03a6-107">命名空間宣告可包含每個宣告類型的任意數目，並依任何順序。</span><span class="sxs-lookup"><span data-stu-id="a03a6-107">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="a03a6-108">請遵循下列連結，以[取得在命名空間中宣告](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)[使用者定義類型](xref:microsoft.quantum.guide.types#user-defined-types)、[作業](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)和函式的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a03a6-108">Follow these links for more details on declaring [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) within a namespace.</span></span>

<span data-ttu-id="a03a6-109">唯一可以出現在命名空間宣告外的文字是批註。</span><span class="sxs-lookup"><span data-stu-id="a03a6-109">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="a03a6-110">特別是在宣告之前，命名空間的檔批註（以下詳細資料）。</span><span class="sxs-lookup"><span data-stu-id="a03a6-110">In particular, documentation comments (more details below) for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="a03a6-111">命名空間宣告</span><span class="sxs-lookup"><span data-stu-id="a03a6-111">Namespace Declarations</span></span>

<span data-ttu-id="a03a6-112">問 # 檔案通常只會有一個命名空間宣告，但可能會有 none （而且是空的或只包含批註），或可能包含多個命名空間。</span><span class="sxs-lookup"><span data-stu-id="a03a6-112">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="a03a6-113">命名空間宣告不可以是嵌套的。</span><span class="sxs-lookup"><span data-stu-id="a03a6-113">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="a03a6-114">同一個命名空間可以宣告在一起編譯的多個 Q # 檔案中，只要沒有任何類型、作業或具有相同名稱的函式宣告即可。</span><span class="sxs-lookup"><span data-stu-id="a03a6-114">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="a03a6-115">特別是，在多個檔案的相同命名空間中定義相同的型別是不正確，即使宣告相同也是一樣。</span><span class="sxs-lookup"><span data-stu-id="a03a6-115">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="a03a6-116">命名空間宣告包含關鍵字 `namespace` ，後面接著命名空間名稱、左大括弧 `{` 、命名空間中包含的宣告和右大括弧 `}` 。</span><span class="sxs-lookup"><span data-stu-id="a03a6-116">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="a03a6-117">命名空間名稱會遵循一或多個以句點分隔之合法符號序列的 .NET 模式 `.` 。</span><span class="sxs-lookup"><span data-stu-id="a03a6-117">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="a03a6-118">例如， `MyQuantumStuff` 和 `Microsoft.Quantum.Intrinsic` 都是有效的命名空間名稱。</span><span class="sxs-lookup"><span data-stu-id="a03a6-118">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="a03a6-119">依照慣例，命名空間名稱中的符號是大寫的，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="a03a6-119">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="a03a6-120">在檔案中進一步宣告之類型或 callables 的參考會正確解析;型別、運算或函式宣告不需要在參考之前。</span><span class="sxs-lookup"><span data-stu-id="a03a6-120">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="a03a6-121">Open 指示詞</span><span class="sxs-lookup"><span data-stu-id="a03a6-121">Open Directives</span></span>

<span data-ttu-id="a03a6-122">在命名空間區塊內，指示詞可用 `open` 來匯入特定命名空間中宣告的所有類型和 callables，並依其不合格的名稱加以參考。</span><span class="sxs-lookup"><span data-stu-id="a03a6-122">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="a03a6-123">這類指示詞 `open` 包含 `open` 關鍵字，後面接著要開啟的命名空間和終止的分號。</span><span class="sxs-lookup"><span data-stu-id="a03a6-123">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="a03a6-124">所有指示詞 `open` 必須出現在 `function` `operation` `newtype` 命名空間區塊中的任何、或宣告之前。</span><span class="sxs-lookup"><span data-stu-id="a03a6-124">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="a03a6-125">（選擇性）可能會定義已開啟之命名空間的簡短名稱，讓來自該命名空間的所有元素都可以（和需要）以定義的簡短名稱限定。</span><span class="sxs-lookup"><span data-stu-id="a03a6-125">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="a03a6-126">例如，假設有下列命名空間宣告和 open 指示詞，</span><span class="sxs-lookup"><span data-stu-id="a03a6-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="a03a6-127">如果我們宣告的作業使用來自的 `Op` 作業 `Microsoft.Quantum.Intrinsic` ，我們只需要使用來呼叫它 `Op` 。</span><span class="sxs-lookup"><span data-stu-id="a03a6-127">if an operation we declare uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, we would call it by simply using `Op`.</span></span>
<span data-ttu-id="a03a6-128">不過，如果我們想要從呼叫特定函 `Fn` 式 `Microsoft.Quantum.Math` ，則需要使用來呼叫它 `Math.Fn` 。</span><span class="sxs-lookup"><span data-stu-id="a03a6-128">However, if we wanted a call a certain function `Fn` from `Microsoft.Quantum.Math`, we would need to call it using `Math.Fn`.</span></span>

<span data-ttu-id="a03a6-129">指示詞 `open` 適用于檔案內的整個命名空間區塊。</span><span class="sxs-lookup"><span data-stu-id="a03a6-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="a03a6-130">因此，如果我們要在與上述相同的問答 # 檔案中定義其他命名空間 `NS` ，則在第二個命名空間中定義的任何作業/函式/類型，都將無法存取來自或的任何專案， `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 除非我們重複其中的 open 指示詞。</span><span class="sxs-lookup"><span data-stu-id="a03a6-130">Hence, if we were to define an additional namespace in the same Q# file as `NS` above, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless we repeated the open directives therein.</span></span> 

<span data-ttu-id="a03a6-131">在*未*于目前命名空間中開啟的另一個命名空間中定義的類型或可呼叫，必須以其完整名稱來參考。</span><span class="sxs-lookup"><span data-stu-id="a03a6-131">A type or callable defined in another namespace that is *not* opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="a03a6-132">例如， `Op` `X.Y` `X.Y.Op` 除非 `X.Y` 先前已在目前區塊中開啟命名空間，否則從命名空間命名的作業必須由其完整名稱參考。</span><span class="sxs-lookup"><span data-stu-id="a03a6-132">For example, an operation named `Op` from the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="a03a6-133">如上所述，即使已 `X` 開啟命名空間，也無法以的形式參考此作業 `Y.Op` 。</span><span class="sxs-lookup"><span data-stu-id="a03a6-133">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="a03a6-134">如果已 `Z` `X.Y` 在該命名空間和檔案中定義的簡短名稱，則必須 `Op` 將稱為 `Z.Op` 。</span><span class="sxs-lookup"><span data-stu-id="a03a6-134">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

<span data-ttu-id="a03a6-135">通常最好是使用指示詞來加入命名空間 `open` 。</span><span class="sxs-lookup"><span data-stu-id="a03a6-135">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="a03a6-136">如果兩個命名空間定義具有相同名稱的結構，而且目前來源使用兩者的結構，則必須使用完整名稱。</span><span class="sxs-lookup"><span data-stu-id="a03a6-136">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="a03a6-137">問 # 遵循與其他 .NET 語言相同的命名規則。</span><span class="sxs-lookup"><span data-stu-id="a03a6-137">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="a03a6-138">不過，Q # 不支援命名空間的相對參考。</span><span class="sxs-lookup"><span data-stu-id="a03a6-138">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="a03a6-139">也就是說，如果已開啟命名空間 `a.b` ，名為之作業的參考 `c.d` 將*不*會解析為具有完整名稱的作業 `a.b.c.d` 。</span><span class="sxs-lookup"><span data-stu-id="a03a6-139">That is, if the namespace `a.b` has been opened, a reference to an operation named `c.d` will *not* be resolved to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="a03a6-140">格式化</span><span class="sxs-lookup"><span data-stu-id="a03a6-140">Formatting</span></span>

<span data-ttu-id="a03a6-141">大部分的 Q # 語句和指示詞的結尾都是終止的分號 `;` 。</span><span class="sxs-lookup"><span data-stu-id="a03a6-141">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="a03a6-142">語句和宣告（如 `for` 和 `operation` ），其結尾為語句區塊（如下所示），不需要終止分號。</span><span class="sxs-lookup"><span data-stu-id="a03a6-142">Statements and declarations such as `for` and `operation` that end with a statement block (see below) do not require a terminating semicolon.</span></span>
<span data-ttu-id="a03a6-143">每個語句描述都會說明結尾分號是否為必要。</span><span class="sxs-lookup"><span data-stu-id="a03a6-143">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="a03a6-144">語句（例如運算式、宣告和指示詞）可能會細分成多行。</span><span class="sxs-lookup"><span data-stu-id="a03a6-144">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="a03a6-145">應避免在單一行上使用多個語句。</span><span class="sxs-lookup"><span data-stu-id="a03a6-145">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="a03a6-146">語句區塊</span><span class="sxs-lookup"><span data-stu-id="a03a6-146">Statement Blocks</span></span>

<span data-ttu-id="a03a6-147">Q # 語句會分組到語句區塊中。</span><span class="sxs-lookup"><span data-stu-id="a03a6-147">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="a03a6-148">語句區塊會以開頭開頭 `{` ，並以結尾結束 `}` 。</span><span class="sxs-lookup"><span data-stu-id="a03a6-148">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="a03a6-149">在另一個區塊中以詞法括住的語句區塊，會被視為包含區塊的子區塊;包含和子區塊也稱為外部和內部區塊。</span><span class="sxs-lookup"><span data-stu-id="a03a6-149">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="a03a6-150">註解</span><span class="sxs-lookup"><span data-stu-id="a03a6-150">Comments</span></span>

<span data-ttu-id="a03a6-151">批註會以兩個正斜線開頭， `//` 並繼續直到行尾為止。</span><span class="sxs-lookup"><span data-stu-id="a03a6-151">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="a03a6-152">批註可能會出現在 Q # 來源檔案中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="a03a6-152">A comment may appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="a03a6-153">文件註解</span><span class="sxs-lookup"><span data-stu-id="a03a6-153">Documentation Comments</span></span>

<span data-ttu-id="a03a6-154">以三個正斜線開頭的批註， `///` 會在它們緊接在命名空間、作業、特製化、函式或類型定義之前，由編譯器特別處理。</span><span class="sxs-lookup"><span data-stu-id="a03a6-154">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="a03a6-155">在此情況下，會將其內容視為已定義之可呼叫或使用者定義類型的檔，就像其他 .NET 語言一樣。</span><span class="sxs-lookup"><span data-stu-id="a03a6-155">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="a03a6-156">在 `///` 批註中，顯示為 API 檔一部分的文字會格式化為[Markdown](https://daringfireball.net/projects/markdown/syntax)，並以特殊命名的標頭指出檔的不同部分。</span><span class="sxs-lookup"><span data-stu-id="a03a6-156">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="a03a6-157">如需 Markdown 的延伸模組，可以使用包含 Q # 中作業、函式和使用者定義類型的交互參考 `@"<ref target>"` ，其中會 `<ref target>` 由所參考之程式碼物件的完整名稱取代。</span><span class="sxs-lookup"><span data-stu-id="a03a6-157">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="a03a6-158">（選擇性）檔引擎也可能支援其他 Markdown 延伸模組。</span><span class="sxs-lookup"><span data-stu-id="a03a6-158">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="a03a6-159">例如：</span><span class="sxs-lookup"><span data-stu-id="a03a6-159">For example:</span></span>

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
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="a03a6-160">下列名稱會被辨識為檔批註標頭。</span><span class="sxs-lookup"><span data-stu-id="a03a6-160">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="a03a6-161">**摘要**：函數或作業行為的簡短摘要，或類型的用途。</span><span class="sxs-lookup"><span data-stu-id="a03a6-161">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="a03a6-162">摘要的第一個段落用於暫留資訊。</span><span class="sxs-lookup"><span data-stu-id="a03a6-162">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="a03a6-163">它應該是純文字。</span><span class="sxs-lookup"><span data-stu-id="a03a6-163">It should be plain text.</span></span>
- <span data-ttu-id="a03a6-164">**描述**：函數或作業行為的描述，或類型的用途說明。</span><span class="sxs-lookup"><span data-stu-id="a03a6-164">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="a03a6-165">摘要和描述會串連，以形成函式、作業或類型所產生的檔檔案。</span><span class="sxs-lookup"><span data-stu-id="a03a6-165">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="a03a6-166">描述可以包含內嵌 LaTeX 格式的符號和方程式。</span><span class="sxs-lookup"><span data-stu-id="a03a6-166">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="a03a6-167">**輸入**：作業或函數之輸入元組的描述。</span><span class="sxs-lookup"><span data-stu-id="a03a6-167">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="a03a6-168">可能包含其他 Markdown 子區段，指示輸入元組的每個個別元素。</span><span class="sxs-lookup"><span data-stu-id="a03a6-168">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="a03a6-169">**輸出**：作業或函式所傳回之元組的描述。</span><span class="sxs-lookup"><span data-stu-id="a03a6-169">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="a03a6-170">**型別參數**：空的區段，其中包含每個泛型型別參數的一個額外子節。</span><span class="sxs-lookup"><span data-stu-id="a03a6-170">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="a03a6-171">**範例**：使用中的作業、函數或類型的簡短範例。</span><span class="sxs-lookup"><span data-stu-id="a03a6-171">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="a03a6-172">**備註**：其他 prose，描述作業、函數或類型的某些層面。</span><span class="sxs-lookup"><span data-stu-id="a03a6-172">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="a03a6-173">**另請參閱**：表示相關函數、作業或使用者定義類型的完整名稱清單。</span><span class="sxs-lookup"><span data-stu-id="a03a6-173">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="a03a6-174">**參考**：要記載之專案的參考和引文清單。</span><span class="sxs-lookup"><span data-stu-id="a03a6-174">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a03a6-175">下一步</span><span class="sxs-lookup"><span data-stu-id="a03a6-175">Next steps</span></span>

<span data-ttu-id="a03a6-176">瞭解 Q # 中的[作業和功能](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="a03a6-176">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>