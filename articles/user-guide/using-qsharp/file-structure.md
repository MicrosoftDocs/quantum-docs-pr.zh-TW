---
title: Q#檔案結構
description: 描述檔案的結構和語法 Q# 。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: ac73962b1a718cd04aa87ee3476c66781fe3ac2b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867925"
---
# <a name="no-locq-file-structure"></a><span data-ttu-id="490e4-103">Q#檔案結構</span><span class="sxs-lookup"><span data-stu-id="490e4-103">Q# File Structure</span></span>

<span data-ttu-id="490e4-104">檔案是 Q# 由一系列的*命名空間*宣告所組成。</span><span class="sxs-lookup"><span data-stu-id="490e4-104">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="490e4-105">每個命名空間宣告都包含使用者定義型別、作業和函式的宣告，而且可以包含每個宣告類型的任意數目和任何順序。</span><span class="sxs-lookup"><span data-stu-id="490e4-105">Each namespace declaration contains declarations for user-defined types, operations, and functions, and can contain any number of each type of declaration and in any order.</span></span>
<span data-ttu-id="490e4-106">如需命名空間內宣告的詳細資訊，請參閱[使用者定義類型](xref:microsoft.quantum.guide.types#user-defined-types)、[作業](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)和[函數](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)。</span><span class="sxs-lookup"><span data-stu-id="490e4-106">For more information on declarations within a namespace, see [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span></span>

<span data-ttu-id="490e4-107">唯一可以出現在命名空間宣告外的文字是批註。</span><span class="sxs-lookup"><span data-stu-id="490e4-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="490e4-108">特別是，命名空間的檔批註會在宣告之前。</span><span class="sxs-lookup"><span data-stu-id="490e4-108">In particular, documentation comments for a namespace precede the declaration.</span></span> <span data-ttu-id="490e4-109">如需詳細資訊，請參閱本文中的[檔批註](#documentation-comments)。</span><span class="sxs-lookup"><span data-stu-id="490e4-109">For more information, see [Documentation comments](#documentation-comments) in this article.</span></span> 

## <a name="namespace-declarations"></a><span data-ttu-id="490e4-110">命名空間宣告</span><span class="sxs-lookup"><span data-stu-id="490e4-110">Namespace Declarations</span></span>

<span data-ttu-id="490e4-111">檔案 Q# 通常只會有一個命名空間宣告，但可能會有 [無] (並空白或只包含批註) 或可能包含多個命名空間。</span><span class="sxs-lookup"><span data-stu-id="490e4-111">A Q# file typically has just one namespace declaration, but could have none (and be empty or just contain comments) or could contain multiple namespaces.</span></span>
<span data-ttu-id="490e4-112">命名空間宣告不能嵌套。</span><span class="sxs-lookup"><span data-stu-id="490e4-112">Namespace declarations can not be nested.</span></span>

<span data-ttu-id="490e4-113">Q#只要沒有任何類型、作業或具有相同名稱的函式宣告，您就可以在一起編譯的多個檔案中宣告相同的命名空間。</span><span class="sxs-lookup"><span data-stu-id="490e4-113">You can declare the same namespace in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="490e4-114">特別是，在多個檔案的相同命名空間中定義相同的型別是不正確，即使宣告相同也是一樣。</span><span class="sxs-lookup"><span data-stu-id="490e4-114">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="490e4-115">命名空間宣告包含關鍵字 `namespace` ，後面接著命名空間的名稱，以及包含在以大括弧括住之命名空間中的宣告 `{ }` 。</span><span class="sxs-lookup"><span data-stu-id="490e4-115">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, and the declarations contained in the namespace enclosed in braces `{ }`.</span></span>
<span data-ttu-id="490e4-116">命名空間名稱會遵循一或多個以句點分隔之合法符號序列的 .NET 模式 `.` 。</span><span class="sxs-lookup"><span data-stu-id="490e4-116">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="490e4-117">例如， `MyQuantumStuff` 和 `Microsoft.Quantum.Intrinsic` 都是有效的命名空間名稱。</span><span class="sxs-lookup"><span data-stu-id="490e4-117">For example, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="490e4-118">依照慣例，會將命名空間名稱中的符號大寫，不過，這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="490e4-118">By convention, capitalize the symbols in a namespace name, however, this is not required.</span></span>

<span data-ttu-id="490e4-119">在檔案中進一步宣告的類型或 callables 的參考已正確解析;型別、運算或函式宣告不需要在參考之前。</span><span class="sxs-lookup"><span data-stu-id="490e4-119">References to types or callables declared further down in a file resolve properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="490e4-120">Open 指示詞</span><span class="sxs-lookup"><span data-stu-id="490e4-120">Open Directives</span></span>

<span data-ttu-id="490e4-121">在命名空間區塊內，使用指示詞彙 `open` 入特定命名空間中宣告的所有類型和 callables，並依其不合格的名稱加以參考。</span><span class="sxs-lookup"><span data-stu-id="490e4-121">Within a namespace block, use the `open` directive to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="490e4-122">這類指示詞 `open` 包含 `open` 關鍵字，後面接著要開啟的命名空間和終止的分號。</span><span class="sxs-lookup"><span data-stu-id="490e4-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="490e4-123">所有指示詞 `open` 必須出現在 `function` `operation` `newtype` 命名空間區塊中的任何、或宣告之前。</span><span class="sxs-lookup"><span data-stu-id="490e4-123">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="490e4-124">（選擇性）您可以為已開啟的命名空間定義簡短名稱。</span><span class="sxs-lookup"><span data-stu-id="490e4-124">Optionally, you can define a short name for the opened namespace.</span></span> <span data-ttu-id="490e4-125">如果定義了簡短名稱，您必須依據定義的簡短名稱，限定該命名空間中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="490e4-125">If a short name is defined, you must qualify all elements from that namespace by the defined short name.</span></span> <span data-ttu-id="490e4-126">例如，假設有下列命名空間宣告和 open 指示詞，</span><span class="sxs-lookup"><span data-stu-id="490e4-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="490e4-127">如果宣告的作業使用來自的 `Op` 作業 `Microsoft.Quantum.Intrinsic` ，您只需要使用來呼叫它 `Op` 。</span><span class="sxs-lookup"><span data-stu-id="490e4-127">if a declared operation uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, you call it by simply using `Op`.</span></span>
<span data-ttu-id="490e4-128">不過，若要從呼叫特定函式 `Fn` `Microsoft.Quantum.Math` ，您必須使用呼叫它 `Math.Fn` 。</span><span class="sxs-lookup"><span data-stu-id="490e4-128">However, to call a certain function `Fn` from `Microsoft.Quantum.Math`, you must call it using `Math.Fn`.</span></span>

<span data-ttu-id="490e4-129">指示詞 `open` 適用于檔案內的整個命名空間區塊。</span><span class="sxs-lookup"><span data-stu-id="490e4-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="490e4-130">因此，如果您在與先前相同的檔案中定義其他命名空間，則在 Q# `NS` 第二個命名空間中定義的任何作業/函式/類型，都不會存取來自或的任何專案， `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 除非您重複其中的 open 指示詞。</span><span class="sxs-lookup"><span data-stu-id="490e4-130">Hence, if you define an additional namespace in the same Q# file as `NS` earlier, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless you repeated the open directives therein.</span></span> 

<span data-ttu-id="490e4-131">若要參考在目前命名空間中*未*開啟的另一個命名空間中定義的類型或可呼叫，您必須以其完整名稱來參考它。</span><span class="sxs-lookup"><span data-stu-id="490e4-131">To reference a type or callable defined in another namespace that is *not* opened in the current namespace, you must reference it by its fully-qualified name.</span></span>
<span data-ttu-id="490e4-132">例如，指定 `Op` 命名空間中的作業 `X.Y` ：</span><span class="sxs-lookup"><span data-stu-id="490e4-132">For example, given an operation named `Op` from the `X.Y` namespace:</span></span>

* <span data-ttu-id="490e4-133">`X.Y.Op`除非 `X.Y` 先前已在目前區塊中開啟命名空間，否則您必須使用完整名稱來參考它。</span><span class="sxs-lookup"><span data-stu-id="490e4-133">You must reference it by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> 
* <span data-ttu-id="490e4-134">即使 `X` 已開啟命名空間，也無法以的形式參考此作業 `Y.Op` 。</span><span class="sxs-lookup"><span data-stu-id="490e4-134">Even if the `X` namespace is opened, it is not possible to reference the operation as `Y.Op`.</span></span>
* <span data-ttu-id="490e4-135">如果您已 `Z` `X.Y` 在該命名空間和檔案中定義的簡短名稱，則必須 `Op` 以形式參考 `Z.Op` 。</span><span class="sxs-lookup"><span data-stu-id="490e4-135">If you defined the short name `Z` for `X.Y` in that namespace and file, you must reference `Op` as `Z.Op`.</span></span> 

<span data-ttu-id="490e4-136">通常最好是使用指示詞來加入命名空間 `open` 。</span><span class="sxs-lookup"><span data-stu-id="490e4-136">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="490e4-137">如果兩個命名空間定義具有相同名稱的結構，而且目前來源使用兩者的結構，則必須使用完整名稱。</span><span class="sxs-lookup"><span data-stu-id="490e4-137">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="490e4-138">Q#遵循與其他 .NET 語言相同的命名規則。</span><span class="sxs-lookup"><span data-stu-id="490e4-138">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="490e4-139">不過，不 Q# 支援命名空間的相對參考。</span><span class="sxs-lookup"><span data-stu-id="490e4-139">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="490e4-140">例如，如果命名空間是開啟的，則名為之作業 `a.b` 的參考不 `c.d` 會解析為具有完整名稱*not*的作業 `a.b.c.d` 。</span><span class="sxs-lookup"><span data-stu-id="490e4-140">For example, if the namespace `a.b` is open, a reference to an operation named `c.d` does *not* resolve to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="490e4-141">格式化</span><span class="sxs-lookup"><span data-stu-id="490e4-141">Formatting</span></span>

<span data-ttu-id="490e4-142">大部分的語句和指示詞的 Q# 結尾都是終止分號 `;` 。</span><span class="sxs-lookup"><span data-stu-id="490e4-142">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="490e4-143">語句和宣告（例如 `for` 和） `operation` 會以語句區塊結束 (請參閱下一節) 不需要終止分號。</span><span class="sxs-lookup"><span data-stu-id="490e4-143">Statements and declarations such as `for` and `operation` that end with a statement block (see the following section) do not require a terminating semicolon.</span></span>
<span data-ttu-id="490e4-144">每個語句描述都會說明結尾分號是否為必要。</span><span class="sxs-lookup"><span data-stu-id="490e4-144">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="490e4-145">語句（例如運算式、宣告和指示詞）可以細分成多行。</span><span class="sxs-lookup"><span data-stu-id="490e4-145">Statements, like expressions, declarations, and directives, can be broken out across multiple lines.</span></span>
<span data-ttu-id="490e4-146">避免將多個語句放在同一行上。</span><span class="sxs-lookup"><span data-stu-id="490e4-146">Avoid putting multiple statements on a single line.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="490e4-147">語句區塊</span><span class="sxs-lookup"><span data-stu-id="490e4-147">Statement Blocks</span></span>

<span data-ttu-id="490e4-148">Q#語句會分組成語句區塊，其包含以大括弧括住 `{ }` 。</span><span class="sxs-lookup"><span data-stu-id="490e4-148">Q# statements are grouped into statement blocks, which are contained with braces `{ }`.</span></span> <span data-ttu-id="490e4-149">語句區塊會以開頭開頭 `{` ，並以結尾結束 `}` 。</span><span class="sxs-lookup"><span data-stu-id="490e4-149">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="490e4-150">在另一個區塊中以詞法括住的語句區塊，會被視為包含區塊的子區塊;包含和子區塊也稱為外部和內部區塊。</span><span class="sxs-lookup"><span data-stu-id="490e4-150">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="490e4-151">註解</span><span class="sxs-lookup"><span data-stu-id="490e4-151">Comments</span></span>

<span data-ttu-id="490e4-152">批註會以兩個正斜線開頭， `//` 並繼續直到行尾為止。</span><span class="sxs-lookup"><span data-stu-id="490e4-152">Comments begin with two forward slashes, `//`, and continue until the end of the line.</span></span>
<span data-ttu-id="490e4-153">批註可以出現在原始檔中的任何位置 Q# 。</span><span class="sxs-lookup"><span data-stu-id="490e4-153">A comment can appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="490e4-154">文件註解</span><span class="sxs-lookup"><span data-stu-id="490e4-154">Documentation Comments</span></span>

<span data-ttu-id="490e4-155">以三個正斜線開頭的批註， `///` 會在它們緊接在命名空間、作業、特製化、函式或類型定義之前，由編譯器特別處理。</span><span class="sxs-lookup"><span data-stu-id="490e4-155">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="490e4-156">在此情況下，編譯器會將它們視為已定義之可呼叫或使用者定義類型的檔，與其他 .NET 語言相同。</span><span class="sxs-lookup"><span data-stu-id="490e4-156">In that case, the compiler treats them as documentation for the defined callable or user-defined type, the same as other .NET languages.</span></span>

<span data-ttu-id="490e4-157">在 `///` 批註中，顯示為 API 檔一部分的文字會格式化為[Markdown](https://daringfireball.net/projects/markdown/syntax)，並以特殊命名的標頭指示不同的檔部分。</span><span class="sxs-lookup"><span data-stu-id="490e4-157">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation indicated by specially-named headers.</span></span>
<span data-ttu-id="490e4-158">在 Markdown 中，使用 `@"<ref target>"` 擴充功能來交互參考中的作業、函式和使用者定義類型 Q# 。</span><span class="sxs-lookup"><span data-stu-id="490e4-158">In Markdown, use the `@"<ref target>"` extension to cross-reference operations, functions, and user-defined types in Q#.</span></span> <span data-ttu-id="490e4-159">取代 `<ref target>` 為所參考程式碼物件的完整名稱。</span><span class="sxs-lookup"><span data-stu-id="490e4-159">Replace `<ref target>` with the fully qualified name of the referenced code object.</span></span>
<span data-ttu-id="490e4-160">不同的檔引擎也可能支援額外的 Markdown 延伸模組。</span><span class="sxs-lookup"><span data-stu-id="490e4-160">Different documentation engines may also support additional Markdown extensions.</span></span>

<span data-ttu-id="490e4-161">例如：</span><span class="sxs-lookup"><span data-stu-id="490e4-161">For example:</span></span>

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

<span data-ttu-id="490e4-162">下列名稱是有效的檔批註標頭。</span><span class="sxs-lookup"><span data-stu-id="490e4-162">The following names are valid as documentation comment headers.</span></span>

- <span data-ttu-id="490e4-163">**摘要**：函數或作業行為的簡短摘要，或類型的用途。</span><span class="sxs-lookup"><span data-stu-id="490e4-163">**Summary**: A short summary of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="490e4-164">摘要的第一個段落用於暫留資訊。</span><span class="sxs-lookup"><span data-stu-id="490e4-164">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="490e4-165">它應該是純文字。</span><span class="sxs-lookup"><span data-stu-id="490e4-165">It should be plain text.</span></span>
- <span data-ttu-id="490e4-166">**描述**：函數或作業行為的描述，或類型的用途。</span><span class="sxs-lookup"><span data-stu-id="490e4-166">**Description**: A description of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="490e4-167">總之，[摘要] 和 [描述] 會形成函數、作業或類型所產生的檔檔案。</span><span class="sxs-lookup"><span data-stu-id="490e4-167">Together, the summary and description form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="490e4-168">此描述支援內嵌 LaTeX 格式的符號和方程式。</span><span class="sxs-lookup"><span data-stu-id="490e4-168">The description supports in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="490e4-169">**輸入**：作業或函數之輸入元組的描述。</span><span class="sxs-lookup"><span data-stu-id="490e4-169">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="490e4-170">可以包含其他 Markdown 子區段，指示輸入元組的每個元素。</span><span class="sxs-lookup"><span data-stu-id="490e4-170">Can contain additional Markdown subsections indicating each element of the input tuple.</span></span>
- <span data-ttu-id="490e4-171">**輸出**：作業或函式所傳回之元組的描述。</span><span class="sxs-lookup"><span data-stu-id="490e4-171">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="490e4-172">**型別參數**：空的區段，其中包含每個泛型型別參數的一個額外子節。</span><span class="sxs-lookup"><span data-stu-id="490e4-172">**Type Parameters**: An empty section that contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="490e4-173">**範例**：使用中的作業、函數或類型的簡短範例。</span><span class="sxs-lookup"><span data-stu-id="490e4-173">**Example**: A short example of the operation, function, or type in use.</span></span>
- <span data-ttu-id="490e4-174">**備註**：其他 prose，描述作業、函數或類型的某些層面。</span><span class="sxs-lookup"><span data-stu-id="490e4-174">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="490e4-175">**另請參閱**：表示相關函數、作業或使用者定義類型的完整名稱清單。</span><span class="sxs-lookup"><span data-stu-id="490e4-175">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="490e4-176">**參考**：已記載專案的參考和引文清單。</span><span class="sxs-lookup"><span data-stu-id="490e4-176">**References**: A list of references and citations for the documented item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="490e4-177">後續步驟</span><span class="sxs-lookup"><span data-stu-id="490e4-177">Next steps</span></span>

<span data-ttu-id="490e4-178">瞭解中的[作業和功能](xref:microsoft.quantum.guide.operationsfunctions) Q# 。</span><span class="sxs-lookup"><span data-stu-id="490e4-178">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>