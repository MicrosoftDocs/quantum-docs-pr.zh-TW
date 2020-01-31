---
title: 檔案結構 |Microsoft Docs
description: 'Q # 檔案結構'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 364d353c55bda38f227456909755d13dc7e67080
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821077"
---
# <a name="file-structure"></a><span data-ttu-id="efdf5-103">檔案結構</span><span class="sxs-lookup"><span data-stu-id="efdf5-103">File Structure</span></span>

<span data-ttu-id="efdf5-104">Q # 檔案是由一系列的命名空間宣告所組成。</span><span class="sxs-lookup"><span data-stu-id="efdf5-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="efdf5-105">每個命名空間宣告都包含使用者定義類型、作業和函式的宣告。</span><span class="sxs-lookup"><span data-stu-id="efdf5-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="efdf5-106">命名空間宣告可包含每個宣告類型的任意數目，並依任何順序。</span><span class="sxs-lookup"><span data-stu-id="efdf5-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="efdf5-107">唯一可以出現在命名空間宣告外的文字是批註。</span><span class="sxs-lookup"><span data-stu-id="efdf5-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="efdf5-108">特別是，命名空間的檔批註會在宣告之前。</span><span class="sxs-lookup"><span data-stu-id="efdf5-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="efdf5-109">命名空間宣告</span><span class="sxs-lookup"><span data-stu-id="efdf5-109">Namespace Declarations</span></span>

<span data-ttu-id="efdf5-110">問 # 檔案通常只會有一個命名空間宣告，但可能會有 none （而且是空的或只包含批註），或可能包含多個命名空間。</span><span class="sxs-lookup"><span data-stu-id="efdf5-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="efdf5-111">命名空間宣告不可以是嵌套的。</span><span class="sxs-lookup"><span data-stu-id="efdf5-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="efdf5-112">同一個命名空間可以宣告在一起編譯的多個 Q # 檔案中，只要沒有任何類型、作業或具有相同名稱的函式宣告即可。</span><span class="sxs-lookup"><span data-stu-id="efdf5-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="efdf5-113">特別是，在多個檔案的相同命名空間中定義相同的型別是不正確，即使宣告相同也是一樣。</span><span class="sxs-lookup"><span data-stu-id="efdf5-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="efdf5-114">命名空間宣告包含關鍵字 `namespace`，後面接著命名空間的名稱、左大括弧 `{`、命名空間中包含的宣告，以及 `}`的右大括弧。</span><span class="sxs-lookup"><span data-stu-id="efdf5-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="efdf5-115">命名空間名稱會遵循一或多個以句點分隔 `.`之合法符號序列的 .NET 模式。</span><span class="sxs-lookup"><span data-stu-id="efdf5-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="efdf5-116">例如，`MyQuantumStuff` 和 `Microsoft.Quantum.Canon` 都是有效的命名空間名稱。</span><span class="sxs-lookup"><span data-stu-id="efdf5-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="efdf5-117">依照慣例，命名空間名稱中的符號是大寫的，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="efdf5-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="efdf5-118">宣告可能會以任何順序出現在命名空間宣告中。</span><span class="sxs-lookup"><span data-stu-id="efdf5-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="efdf5-119">在檔案中進一步宣告之類型或 callables 的參考會正確解析;型別、運算或函式宣告不需要在參考之前。</span><span class="sxs-lookup"><span data-stu-id="efdf5-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="efdf5-120">Open 指示詞</span><span class="sxs-lookup"><span data-stu-id="efdf5-120">Open Directives</span></span>

<span data-ttu-id="efdf5-121">在命名空間區塊內，`open` 指示詞可用來匯入特定命名空間中定義的所有類型和 callables，並依其不合格的名稱加以參考。</span><span class="sxs-lookup"><span data-stu-id="efdf5-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="efdf5-122">這類 `open` 指示詞是由 `open` 關鍵字組成，後面接著要開啟的命名空間和結束的分號。</span><span class="sxs-lookup"><span data-stu-id="efdf5-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="efdf5-123">例如，</span><span class="sxs-lookup"><span data-stu-id="efdf5-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="efdf5-124">（選擇性）可能會定義已開啟之命名空間的簡短名稱，讓來自該命名空間的所有元素都可以（和需要）以定義的簡短名稱限定。</span><span class="sxs-lookup"><span data-stu-id="efdf5-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="efdf5-125">這種簡短名稱的定義方式是在 `open` 指示詞中的分號前面加上關鍵字 `as` 後面接著所需的簡短名稱：</span><span class="sxs-lookup"><span data-stu-id="efdf5-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="efdf5-126">所有的 `open` 指示詞都必須出現在命名空間區塊中的任何 `function`、`operation`或 `newtype` 宣告之前。</span><span class="sxs-lookup"><span data-stu-id="efdf5-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="efdf5-127">`open` 指示詞適用于檔案內的整個命名空間區塊。</span><span class="sxs-lookup"><span data-stu-id="efdf5-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="efdf5-128">使用者定義型別宣告</span><span class="sxs-lookup"><span data-stu-id="efdf5-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="efdf5-129">問 # 提供一種方式，讓使用者宣告新的使用者定義型別，如[Q # 型別模型](xref:microsoft.quantum.language.type-model)一節中所述。</span><span class="sxs-lookup"><span data-stu-id="efdf5-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="efdf5-130">即使基底類型完全相同，使用者定義類型也是相異的。</span><span class="sxs-lookup"><span data-stu-id="efdf5-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="efdf5-131">特別是，兩個使用者自訂類型的值之間不會自動轉換，即使基礎類型相同也一樣。</span><span class="sxs-lookup"><span data-stu-id="efdf5-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="efdf5-132">使用者定義型別宣告包含關鍵字 `newtype`，後面接著使用者定義型別的名稱、`=`、有效的型別規格和終止的分號。</span><span class="sxs-lookup"><span data-stu-id="efdf5-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="efdf5-133">例如：</span><span class="sxs-lookup"><span data-stu-id="efdf5-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="efdf5-134">每個 Q # 來源檔案都可以宣告任何數目的使用者定義類型。</span><span class="sxs-lookup"><span data-stu-id="efdf5-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="efdf5-135">類型名稱在命名空間中必須是唯一的，而且可能不會與作業和函式名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="efdf5-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="efdf5-136">無法定義使用者定義類型之間的迴圈相依性。</span><span class="sxs-lookup"><span data-stu-id="efdf5-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="efdf5-137">因此，不可能在 Q # 內進行遞迴類型。</span><span class="sxs-lookup"><span data-stu-id="efdf5-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="efdf5-138">作業宣告</span><span class="sxs-lookup"><span data-stu-id="efdf5-138">Operation Declarations</span></span>

<span data-ttu-id="efdf5-139">作業是 Q # 的核心，大致類似于其他語言的函式。</span><span class="sxs-lookup"><span data-stu-id="efdf5-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="efdf5-140">每個 Q # 來源檔案都可以定義任何數目的作業。</span><span class="sxs-lookup"><span data-stu-id="efdf5-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="efdf5-141">作業名稱在命名空間中必須是唯一的，而且可能不會與型別和函式名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="efdf5-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="efdf5-142">作業宣告包含關鍵字 `operation`，後面接著是作業名稱的符號、定義作業之引數的具類型識別碼元組、冒號 `:`、描述作業結果類型的類型注釋、選擇性具有作業特性的注釋、左括弧 `{`、作業宣告的主體，以及最後的右大括弧 `}`。</span><span class="sxs-lookup"><span data-stu-id="efdf5-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="efdf5-143">作業宣告的主體是由預設的實值或特製化清單所組成。</span><span class="sxs-lookup"><span data-stu-id="efdf5-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="efdf5-144">如果只需要明確指定預設主體特製化的執行，則可以在宣告中直接指定預設的實值。</span><span class="sxs-lookup"><span data-stu-id="efdf5-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="efdf5-145">在此情況下，在宣告中具有作業特性的注釋，有助於確保編譯器會根據預設的執行自動產生其他特製化。</span><span class="sxs-lookup"><span data-stu-id="efdf5-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="efdf5-146">例如：</span><span class="sxs-lookup"><span data-stu-id="efdf5-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="efdf5-147">作業特性定義哪些類型的函子可套用至已宣告的作業，以及它們有何影響。</span><span class="sxs-lookup"><span data-stu-id="efdf5-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="efdf5-148">如果作業會執行單一轉換，則可以定義作業在*adjointed*或*控制*時的運作方式。</span><span class="sxs-lookup"><span data-stu-id="efdf5-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="efdf5-149">這些特製化的存在可以宣告為作業簽章的一部分。</span><span class="sxs-lookup"><span data-stu-id="efdf5-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="efdf5-150">然後編譯器會產生每個這類隱含宣告特製化的對應執行。</span><span class="sxs-lookup"><span data-stu-id="efdf5-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="efdf5-151">在上述範例中，編譯器會產生 adjoint、受控制和受控制的 adjoint 特製化。</span><span class="sxs-lookup"><span data-stu-id="efdf5-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="efdf5-152">如果編譯器無法產生執行，則可以明確指定。</span><span class="sxs-lookup"><span data-stu-id="efdf5-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="efdf5-153">這種明確的特製化宣告可以包含適當的世代指示詞，以清楚瞭解如何建立特定特製化，或使用者定義的實作為方式。</span><span class="sxs-lookup"><span data-stu-id="efdf5-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="efdf5-154">範例中 `PrepareEntangledPair` 的程式碼相當於下列程式碼，其中包含明確的特製化宣告：</span><span class="sxs-lookup"><span data-stu-id="efdf5-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="efdf5-155">關鍵字 `auto` 表示編譯器應該決定如何產生特製化執行。</span><span class="sxs-lookup"><span data-stu-id="efdf5-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="efdf5-156">如果編譯器無法產生特定特製化的實作為，而沒有進一步的指示（例如更精確的產生指示詞），或如果可以指定更有效率的執行，則也可以手動定義執行。</span><span class="sxs-lookup"><span data-stu-id="efdf5-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

<span data-ttu-id="efdf5-157">在上述範例中，`adjoint invert;` 指出 adjoint 特製化是藉由將主體實作為反轉而產生，`controlled adjoint invert;` 表示會藉由反轉受控制特製化的指定實作為來產生受控制的 adjoint 特製化。</span><span class="sxs-lookup"><span data-stu-id="efdf5-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="efdf5-158">若要支援 `Adjoint` 和/或 `Controlled` 仿函數之應用程式的作業，其傳回型別一定要 `Unit`。</span><span class="sxs-lookup"><span data-stu-id="efdf5-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="efdf5-159">明確特製化宣告</span><span class="sxs-lookup"><span data-stu-id="efdf5-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="efdf5-160">Q # 作業可以包含下列明確的特製化宣告：</span><span class="sxs-lookup"><span data-stu-id="efdf5-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="efdf5-161">`body` 特製化會指定未套用任何函子之作業的執行。</span><span class="sxs-lookup"><span data-stu-id="efdf5-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="efdf5-162">`adjoint` 特製化會指定套用 `Adjoint` 仿函數之作業的執行。</span><span class="sxs-lookup"><span data-stu-id="efdf5-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="efdf5-163">`controlled` 特製化會指定套用 `Controlled` 仿函數之作業的執行。</span><span class="sxs-lookup"><span data-stu-id="efdf5-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="efdf5-164">`controlled adjoint` 特製化會指定套用 `Adjoint` 和 `Controlled` 函子的作業執行。</span><span class="sxs-lookup"><span data-stu-id="efdf5-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="efdf5-165">此特製化也可以命名為 `adjoint controlled`，因為這兩個函子會向後。</span><span class="sxs-lookup"><span data-stu-id="efdf5-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="efdf5-166">作業特製化包含特製化標記（例如 `body`或 `adjoint`等），後面接著下列其中一個：</span><span class="sxs-lookup"><span data-stu-id="efdf5-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="efdf5-167">明確宣告，如下所述。</span><span class="sxs-lookup"><span data-stu-id="efdf5-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="efdf5-168">指示編譯器如何產生特製化的指示詞，這是下列其中一個：</span><span class="sxs-lookup"><span data-stu-id="efdf5-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="efdf5-169">`intrinsic`，表示特製化是由目的電腦所提供。</span><span class="sxs-lookup"><span data-stu-id="efdf5-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="efdf5-170">`distribute`，可與 `controlled` 和 `controlled adjoint` 特殊化搭配使用。</span><span class="sxs-lookup"><span data-stu-id="efdf5-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="efdf5-171">與 `controlled`搭配使用時，它會指出編譯器應該藉由將 `Controlled` 套用至 `body`中的所有作業來計算特製化。</span><span class="sxs-lookup"><span data-stu-id="efdf5-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="efdf5-172">與 `controlled adjoint`搭配使用時，它會指出編譯器應該藉由將 `Controlled` 套用至 `adjoint` 特製化中的所有作業來計算特製化。</span><span class="sxs-lookup"><span data-stu-id="efdf5-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="efdf5-173">`invert`，表示編譯器應該藉由反轉 `body`來計算 `adjoint` 特製化，亦即反轉作業的順序，並將 adjoint 套用至每一個。</span><span class="sxs-lookup"><span data-stu-id="efdf5-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="efdf5-174">與 `adjoint controlled`搭配使用時，這表示編譯器應該藉由反轉 `controlled` 特製化來計算特製化。</span><span class="sxs-lookup"><span data-stu-id="efdf5-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="efdf5-175">`self`，表示 adjoint 特製化與 `body` 特製化相同。</span><span class="sxs-lookup"><span data-stu-id="efdf5-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="efdf5-176">這對於 `adjoint` 和 `adjoint controlled` 特製化而言是合法的。</span><span class="sxs-lookup"><span data-stu-id="efdf5-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="efdf5-177">針對 `adjoint controlled`，`self` 表示 `adjoint controlled` 特製化與 `controlled` 特製化相同。</span><span class="sxs-lookup"><span data-stu-id="efdf5-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="efdf5-178">`auto`，表示編譯器應該選取要套用的適當指示詞。</span><span class="sxs-lookup"><span data-stu-id="efdf5-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="efdf5-179">`auto` 可能無法用於 `body` 特製化。</span><span class="sxs-lookup"><span data-stu-id="efdf5-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="efdf5-180">指示詞和 `auto` 都需要結尾的分號 `;`。</span><span class="sxs-lookup"><span data-stu-id="efdf5-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="efdf5-181">如果提供 `body` 的明確宣告，`auto` 指示詞會解析為下列層代指示詞：</span><span class="sxs-lookup"><span data-stu-id="efdf5-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="efdf5-182">`adjoint` 特製化是根據指示詞 `invert`所產生。</span><span class="sxs-lookup"><span data-stu-id="efdf5-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="efdf5-183">`controlled` 特製化是根據指示詞 `distribute`所產生。</span><span class="sxs-lookup"><span data-stu-id="efdf5-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="efdf5-184">`adjoint controlled` 特製化是根據指示詞所產生 `invert` 如果指定了 `controlled` 的明確宣告，但不是 `adjoint`的宣告，則為，否則 `distribute`。</span><span class="sxs-lookup"><span data-stu-id="efdf5-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="efdf5-185">如果作業是自行 adjoint 的，請透過產生指示詞明確指定 adjoint 或受控制的 adjoint 特製化 `self`，讓編譯器能夠使用該資訊來進行優化。</span><span class="sxs-lookup"><span data-stu-id="efdf5-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="efdf5-186">包含使用者定義之實作為的特製化宣告，是由引數元組後面接著語句區塊，以及用來實行特製化的 Q # 程式碼所組成。</span><span class="sxs-lookup"><span data-stu-id="efdf5-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="efdf5-187">在引數清單中，`...` 是用來代表為整個作業所宣告的引數。</span><span class="sxs-lookup"><span data-stu-id="efdf5-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="efdf5-188">對於 `body` 和 `adjoint`而言，引數清單應一律 `(...)`;對於 `controlled` 和 `adjoint controlled`，引數清單應該是代表控制項 qubits 陣列的符號，後面接著 `...`，並以括弧括住;例如，`(controls,...)`。</span><span class="sxs-lookup"><span data-stu-id="efdf5-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="efdf5-189">如果需要明確宣告預設主體以外的一個或多個特製化，則預設主體的執行也必須包裝為適當的特製化宣告：</span><span class="sxs-lookup"><span data-stu-id="efdf5-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a><span data-ttu-id="efdf5-190">Adjoint</span><span class="sxs-lookup"><span data-stu-id="efdf5-190">Adjoint</span></span>

<span data-ttu-id="efdf5-191">作業的 adjoint 會指定如何實作為運算的複雜共軛轉置，也就是「反向執行」時作業的運作方式。</span><span class="sxs-lookup"><span data-stu-id="efdf5-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="efdf5-192">指定不含 adjoint 的作業是合法的;例如，量測作業沒有 adjoint，因為它們無法反轉。</span><span class="sxs-lookup"><span data-stu-id="efdf5-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="efdf5-193">如果作業的宣告包含 adjoint 特製化的隱含或明確宣告，則作業支援 `Adjoint` 仿函數。</span><span class="sxs-lookup"><span data-stu-id="efdf5-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="efdf5-194">明確宣告的受控制 adjoint 特製化表示 adjoint 特製化的存在。</span><span class="sxs-lookup"><span data-stu-id="efdf5-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="efdf5-195">如果作業的主體包含重複執行迴圈、set 語句、量值、傳回語句，或呼叫不支援 `Adjoint` 仿函數的其他作業，則不可能 `invert` 或 `auto` 指示詞之後自動產生 adjoint 特製化。</span><span class="sxs-lookup"><span data-stu-id="efdf5-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="efdf5-196">管理</span><span class="sxs-lookup"><span data-stu-id="efdf5-196">Controlled</span></span>

<span data-ttu-id="efdf5-197">作業的受控制版本會指定如何實作用配量控制版本的作業，亦即作業在配量暫存器的狀態下套用時的運作方式。</span><span class="sxs-lookup"><span data-stu-id="efdf5-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="efdf5-198">[[控制](xref:microsoft.quantum.language.type-model#controlled)] 區段中會提供更完整的描述。</span><span class="sxs-lookup"><span data-stu-id="efdf5-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="efdf5-199">指定沒有受控制版本的作業是合法的：例如，測量作業沒有受控制的版本，因為它們無法控制。</span><span class="sxs-lookup"><span data-stu-id="efdf5-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="efdf5-200">作業只有在其宣告包含受控制特製化的隱含或明確宣告時，才支援 `Controlled` 仿函數。</span><span class="sxs-lookup"><span data-stu-id="efdf5-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="efdf5-201">明確宣告的受控制 adjoint 特製化表示已控制特製化的存在。</span><span class="sxs-lookup"><span data-stu-id="efdf5-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="efdf5-202">對於本文包含不支援 `Controlled` 仿函數之其他作業的呼叫，不可能在 `distribute` 或 `auto` 指示詞之後自動產生受控制的特製化。</span><span class="sxs-lookup"><span data-stu-id="efdf5-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="efdf5-203">控制的 Adjoint</span><span class="sxs-lookup"><span data-stu-id="efdf5-203">Controlled Adjoint</span></span>

<span data-ttu-id="efdf5-204">作業的受控制 adjoint 版本會指定如何實作為作業 adjoint 的配量控制版本。</span><span class="sxs-lookup"><span data-stu-id="efdf5-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="efdf5-205">指定沒有受控制 adjoint 版本的作業是合法的：比方說，測量作業沒有受控制的 adjoint 版本，因為它們都不是可控制也不可逆。</span><span class="sxs-lookup"><span data-stu-id="efdf5-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="efdf5-206">只有在 adjoint 和受控制的特製化都存在時，作業的受控制 adjoint 特製化才需要存在。</span><span class="sxs-lookup"><span data-stu-id="efdf5-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="efdf5-207">在這種情況下，系統會推斷受控制的 adjoint 特製化，而且編譯器會產生適當的特製化（如果未明確定義任何實作為）。</span><span class="sxs-lookup"><span data-stu-id="efdf5-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="efdf5-208">若作業的內文包含的呼叫不具有受控制 adjoint 版本的其他作業，則不能在 `invert`之後自動產生 adjoint 特製化，`distribute` 或 `auto` 指示詞。</span><span class="sxs-lookup"><span data-stu-id="efdf5-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="efdf5-209">範例</span><span class="sxs-lookup"><span data-stu-id="efdf5-209">Examples</span></span>

<span data-ttu-id="efdf5-210">作業宣告可能會像下面這樣簡單，其定義基本的 Pauli X 運算：</span><span class="sxs-lookup"><span data-stu-id="efdf5-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="efdf5-211">以下定義了「傳送」作業。</span><span class="sxs-lookup"><span data-stu-id="efdf5-211">The following defines the teleport operation.</span></span>

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a><span data-ttu-id="efdf5-212">函式宣告</span><span class="sxs-lookup"><span data-stu-id="efdf5-212">Function Declarations</span></span>

<span data-ttu-id="efdf5-213">函式在 Q # 中純粹是傳統的常式。</span><span class="sxs-lookup"><span data-stu-id="efdf5-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="efdf5-214">每個 Q # 來源檔案可能會定義任意數目的函數。</span><span class="sxs-lookup"><span data-stu-id="efdf5-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="efdf5-215">函式宣告包含關鍵字 `function`，後面接著是函式名稱的符號、具類型的識別碼元組、描述函數傳回類型的類型注釋，以及描述函式執行的語句區塊。</span><span class="sxs-lookup"><span data-stu-id="efdf5-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="efdf5-216">定義函式的語句區塊必須括在 `{` 中，而 `}` 就像任何其他語句區塊一樣。</span><span class="sxs-lookup"><span data-stu-id="efdf5-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="efdf5-217">函數名稱在命名空間中必須是唯一的，而且可能不會與作業和類型名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="efdf5-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="efdf5-218">函式可能不會配置或借用 qubits，或呼叫作業。</span><span class="sxs-lookup"><span data-stu-id="efdf5-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="efdf5-219">作業的部分應用，或傳遞操作類型的值是正常的。</span><span class="sxs-lookup"><span data-stu-id="efdf5-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="efdf5-220">例如，</span><span class="sxs-lookup"><span data-stu-id="efdf5-220">For example,</span></span>

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```
