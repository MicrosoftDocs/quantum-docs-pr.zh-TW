---
title: 參與 Microsoft QDK 的檔
description: 瞭解如何將概念或 API 內容提供給 Microsoft 量子檔集。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: ed5ab5df9de5d71ccd922cd430cf15779806dd6a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274553"
---
# <a name="improving-documentation"></a><span data-ttu-id="79c82-103">改善文件</span><span class="sxs-lookup"><span data-stu-id="79c82-103">Improving Documentation</span></span>

<span data-ttu-id="79c82-104">量子開發工具組的檔會採用數種不同的形式，讓量子開發人員可以立即使用該資訊。</span><span class="sxs-lookup"><span data-stu-id="79c82-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="79c82-105">遵循檔的原則[做為程式碼](https://www.writethedocs.org/guide/docs-as-code/)，所有的配量開發工具組檔都會格式化為程式碼，並使用 Git 進行管理，其方式與用來建立量子開發工具組的原始程式碼相同。</span><span class="sxs-lookup"><span data-stu-id="79c82-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="79c82-106">在大部分的情況下，程式碼支援檔是由各種形式的[Markdown](https://daringfireball.net/projects/markdown/)所組成，這是一種語言，用來以純文字格式寫出豐富格式的文字，可在命令列、ide 和原始檔控制中輕鬆使用。</span><span class="sxs-lookup"><span data-stu-id="79c82-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="79c82-107">我們同樣採用[MathJax](https://www.mathjax.org/)程式庫，以允許在檔中使用 LaTeX 語言來格式化數學法，如下所詳述。</span><span class="sxs-lookup"><span data-stu-id="79c82-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="79c82-108">話雖如此，每一種形式的檔都有不同的細節：</span><span class="sxs-lookup"><span data-stu-id="79c82-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="79c82-109">**概念檔**包含發行至的一系列文章 https://docs.microsoft.com/quantum ，並說明從量子計算的基本概念到交換格式的技術規格等所有事項。</span><span class="sxs-lookup"><span data-stu-id="79c82-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="79c82-110">這些文章是以[DocFX-Flavored Markdown （DFM）](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)撰寫，這是用來建立豐富檔集的 Markdown 變體。</span><span class="sxs-lookup"><span data-stu-id="79c82-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="79c82-111">**API 參考**是每個 Q # 函數、作業和使用者定義類型的一組頁面，已發行至 https://docs.microsoft.com/qsharp/api/ 。</span><span class="sxs-lookup"><span data-stu-id="79c82-111">The **API reference** is a set of pages for each Q# function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="79c82-112">這些頁面會記錄每個可呼叫的輸入和作業，以及範例和詳細資訊的連結。</span><span class="sxs-lookup"><span data-stu-id="79c82-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="79c82-113">API 參考會在每次發行時，從 Q # 原始程式碼中的小型 DFM 檔自動解壓縮。</span><span class="sxs-lookup"><span data-stu-id="79c82-113">The API reference is automatically extracted from small DFM documents in Q# source code as a part of each release.</span></span>
- <span data-ttu-id="79c82-114">每個範例和 kata 中包含的\*\*readme.txt <!----> \*\*檔案，會說明如何使用該範例或 kata、其涵蓋的內容，以及它與其他的量子開發工具組的關係。</span><span class="sxs-lookup"><span data-stu-id="79c82-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="79c82-115">這些檔案是使用[GitHub Flavored Markdown （GFM）](https://github.github.com/gfm/)所撰寫，這是更輕量的替代方案，可將檔直接附加至程式碼存放庫。</span><span class="sxs-lookup"><span data-stu-id="79c82-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="79c82-116">參與概念檔</span><span class="sxs-lookup"><span data-stu-id="79c82-116">Contributing to the Conceptual Documentation</span></span>

<span data-ttu-id="79c82-117">為了提供概念或讀我檔案的改進，在適當的情況下，您可以根據[**MicrosoftDocs/量子-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
)、 [**microsoft/量子**](https://github.com/Microsoft/Quantum)或[**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas)，以提取要求開始。</span><span class="sxs-lookup"><span data-stu-id="79c82-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="79c82-118">我們將在下方說明提取要求的詳細資訊，但現在有幾件事可以在改善檔時記住：</span><span class="sxs-lookup"><span data-stu-id="79c82-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="79c82-119">讀者會從非常廣泛的背景，進入「量子開發工具組」檔。</span><span class="sxs-lookup"><span data-stu-id="79c82-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="79c82-120">來自高中學生的每個人，想要學習新功能和令人興奮的任職教職員執行量子運算研究時，應該能夠取得閱讀檔的相關內容。</span><span class="sxs-lookup"><span data-stu-id="79c82-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="79c82-121">在可能的範圍內，請不要對讀者的部分取得豐富的知識，因為它們可能只是從開始。如果您可以提供清楚且可存取的描述，或者可以提供其他資源的連結以取得詳細資訊，它最有説明。</span><span class="sxs-lookup"><span data-stu-id="79c82-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="79c82-122">檔集並不像書籍或論文一樣，而讀者會收到「中間」這類的內容。</span><span class="sxs-lookup"><span data-stu-id="79c82-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="79c82-123">例如，搜尋引擎可能不會建議索引，也可能是由朋友傳送連結來嘗試協助他們。請一律提供清楚的內容，以及適當的連結，以協助您的讀者。</span><span class="sxs-lookup"><span data-stu-id="79c82-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="79c82-124">有些讀者會發現抽象的語句和定義最有説明，而其他讀取器則是從具體範例中推斷的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="79c82-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="79c82-125">同時提供一般案例和特定範例，可協助這兩個讀取器充分利用量副程式設計。</span><span class="sxs-lookup"><span data-stu-id="79c82-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="79c82-126">特別是當您也寫了記載的程式碼時，您可能會很明顯地得知您的讀者並不清楚。</span><span class="sxs-lookup"><span data-stu-id="79c82-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="79c82-127">沒有一種獨特的程式設計方法，因此無論讀者有多麼聰明或有經驗，他們都無法猜出您在程式碼中最有説明的設計模式。</span><span class="sxs-lookup"><span data-stu-id="79c82-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="79c82-128">清楚瞭解讀取器可以如何利用您的程式碼來協助提供該內容。</span><span class="sxs-lookup"><span data-stu-id="79c82-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="79c82-129">「量副程式設計」小組的許多成員都是學術研究人員，主要是透過對其投稿貢獻的引文來辨識。</span><span class="sxs-lookup"><span data-stu-id="79c82-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="79c82-130">除了協助讀者尋找額外的資料之外，也請務必適當地提及學術的輸出（例如論文、交談、blog 文章和軟體工具），以協助學術參與者繼續進行最佳的工作來改善社區。</span><span class="sxs-lookup"><span data-stu-id="79c82-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="79c82-131">「量副程式設計」小組是廣泛而 wonderfully 的多樣化團體。</span><span class="sxs-lookup"><span data-stu-id="79c82-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="79c82-132">使用協力廠商範例中的名詞代名詞（例如：「如果使用者 ...，他將 ...」）可以工作來排除而不是包含。</span><span class="sxs-lookup"><span data-stu-id="79c82-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="79c82-133">在引文和連結中 cognizant 人員名稱，以及正確包含非 ASCII 字元，可以藉由顯示其成員來提供社區的多樣性。</span><span class="sxs-lookup"><span data-stu-id="79c82-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="79c82-134">同樣地，英文語言中的許多單字通常會以 hateful 的方式使用，因此在技術檔中使用時，可能會對個別讀者和大型團體造成損害。</span><span class="sxs-lookup"><span data-stu-id="79c82-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

### <a name="referencing-sample-code-from-conceptual-articles"></a><span data-ttu-id="79c82-135">參考概念文章中的範例程式碼</span><span class="sxs-lookup"><span data-stu-id="79c82-135">Referencing Sample Code from Conceptual Articles</span></span>

<span data-ttu-id="79c82-136">如果您想要包含[範例存放庫](https://github.com/Microsoft/Quantum)中的程式碼，您可以使用特殊的 DocFX-Flavored Markdown 命令來執行此動作：</span><span class="sxs-lookup"><span data-stu-id="79c82-136">If you want to include code from the [samples repository](https://github.com/Microsoft/Quantum), you can do so using a special DocFX-Flavored Markdown command:</span></span>

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

<span data-ttu-id="79c82-137">此命令會[ `Game.qs` 從 `chsh-game` 範例](https://github.com/microsoft/Quantum/blob/master/samples/algorithms/chsh-game/Game.qs)匯入行4到8的檔案，並將其標示為 Q # 程式碼以進行語法醒目提示。</span><span class="sxs-lookup"><span data-stu-id="79c82-137">This command will import lines 4 to 8 of the [`Game.qs` file from the `chsh-game` sample](https://github.com/microsoft/Quantum/blob/master/samples/algorithms/chsh-game/Game.qs), marking them as Q# code for the purpose of syntax highlighting.</span></span>
<span data-ttu-id="79c82-138">使用此命令，您可以避免在概念文章和範例存放庫之間複製程式碼，讓檔中的範例程式碼一律盡可能保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="79c82-138">Using this command, you can avoid duplicating code between conceptual articles and the samples repository, so that sample code in documentation is always as up to date as possible.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="79c82-139">參與 API 參考</span><span class="sxs-lookup"><span data-stu-id="79c82-139">Contributing to the API References</span></span>

<span data-ttu-id="79c82-140">若要改善 API 參考的效果，在記載的程式碼上直接開啟提取要求最有説明。</span><span class="sxs-lookup"><span data-stu-id="79c82-140">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="79c82-141">每個函式、作業或使用者定義類型都支援檔批註（以表示， `///` 而不是 `//` ）。</span><span class="sxs-lookup"><span data-stu-id="79c82-141">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="79c82-142">當我們編譯每個版本的「配量」開發工具組時，會使用這些批註來產生的 API 參考， https://docs.microsoft.com/qsharp/api/ 包括每個可呼叫之輸入和輸出的詳細資料，以及每個可呼叫的假設，以及如何使用它們的範例。</span><span class="sxs-lookup"><span data-stu-id="79c82-142">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79c82-143">請務必不要手動編輯產生的 API 檔，因為每個新版本都會覆寫這些檔案。</span><span class="sxs-lookup"><span data-stu-id="79c82-143">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="79c82-144">我們將您對您的貢獻做為價值，並想要確保您的變更在發行後仍持續協助使用者發行。</span><span class="sxs-lookup"><span data-stu-id="79c82-144">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="79c82-145">例如，請考慮函數 `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="79c82-145">For example, consider the function `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="79c82-146">檔批註應該可以協助使用者瞭解如何解讀 `bits` 和功能的 `oracle` 用途。</span><span class="sxs-lookup"><span data-stu-id="79c82-146">A documentation comment should help a user learn how to interpret `bits` and `oracle` and what the function is for.</span></span>
<span data-ttu-id="79c82-147">您可以透過檔批註中特別命名的 Markdown 區段，將這些不同的資訊片段提供給 Q # 編譯器。</span><span class="sxs-lookup"><span data-stu-id="79c82-147">Each of these different pieces of information can be provided to the Q# compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="79c82-148">在的範例 `ControlledOnBitString` 中，我們可能會撰寫如下所示的內容：</span><span class="sxs-lookup"><span data-stu-id="79c82-148">For the example of `ControlledOnBitString`, we might write something like the following:</span></span>

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

<span data-ttu-id="79c82-149">您可以在函式的 API 檔中查看上述程式碼的呈現版本。 [ `ControlledOnBitString` ](xref:microsoft.quantum.canon.controlledonbitstring)</span><span class="sxs-lookup"><span data-stu-id="79c82-149">You can see the rendered version of the code above in the [API documentation for the `ControlledOnBitString` function](xref:microsoft.quantum.canon.controlledonbitstring).</span></span>

<span data-ttu-id="79c82-150">除了撰寫檔的一般作法外，在撰寫 API 檔批註時，您可以記住一些事項：</span><span class="sxs-lookup"><span data-stu-id="79c82-150">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="79c82-151">每個檔批註的格式必須符合 Q # 編譯器所預期的檔，才能正確顯示。</span><span class="sxs-lookup"><span data-stu-id="79c82-151">The format of each documentation comment has to match what the Q# compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="79c82-152">某些區段（例如 `/// # Remarks` 允許自由格式內容），而區段之類的區段 `/// # See Also` 則較為嚴格。</span><span class="sxs-lookup"><span data-stu-id="79c82-152">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="79c82-153">讀者可以在主要 API 參考網站上、每個命名空間的摘要，或甚至是透過使用暫留資訊，從其 IDE 中讀取您的 API 檔。</span><span class="sxs-lookup"><span data-stu-id="79c82-153">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="79c82-154">請確定 `/// # Summary` 不超過句子的長度可協助您的讀者快速地排序它們是否需要進一步閱讀或查看其他位置，並可協助快速透過命名空間摘要進行掃描。</span><span class="sxs-lookup"><span data-stu-id="79c82-154">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="79c82-155">您的檔可能會比程式碼本身更長，但也沒關係！</span><span class="sxs-lookup"><span data-stu-id="79c82-155">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="79c82-156">即使是一小段程式碼，對不知道該程式碼所在內容的使用者，也可能會產生非預期的影響。</span><span class="sxs-lookup"><span data-stu-id="79c82-156">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="79c82-157">藉由提供具體的範例和清楚的說明，您可以協助使用者充分利用其所提供的程式碼。</span><span class="sxs-lookup"><span data-stu-id="79c82-157">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
