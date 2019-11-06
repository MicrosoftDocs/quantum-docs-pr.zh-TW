---
title: '問 # 樣式指南 |Microsoft Docs'
description: '問 # 樣式指南'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 4050e2ee9e516aed7a8ba1398792562926808ee0
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463315"
---
# <a name="q-style-guide"></a><span data-ttu-id="0d5e2-103">問 # 樣式指南</span><span class="sxs-lookup"><span data-stu-id="0d5e2-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="0d5e2-104">一般慣例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-104">General Conventions</span></span> ##

<span data-ttu-id="0d5e2-105">本指南中所建議的慣例旨在協助您更容易閱讀和瞭解以 Q # 撰寫的程式和程式庫。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="0d5e2-106">指導方針</span><span class="sxs-lookup"><span data-stu-id="0d5e2-106">Guidance</span></span>

<span data-ttu-id="0d5e2-107">我們建議：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-107">We suggest:</span></span>

- <span data-ttu-id="0d5e2-108">絕對不要忽略慣例，除非您故意這麼做，才能為使用者提供更容易閱讀且易於理解的程式碼。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="0d5e2-109">命名慣例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-109">Naming Conventions</span></span> ##

<span data-ttu-id="0d5e2-110">在提供配量開發工具組的同時，我們致力於功能和作業名稱，協助量子開發人員撰寫容易閱讀的程式，並將驚訝降到最低。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="0d5e2-111">其中一個重要的部分是，當我們選擇函式、作業和類型的名稱時，我們會建立程式設計人員用來表達量子概念的*詞彙*;透過我們的選擇，我們可以協助或妨礙他們的工作，以清楚溝通。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="0d5e2-112">這會讓我們負責確保引進的名稱提供清楚明瞭，而不是隱匿。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="0d5e2-113">在本節中，我們將詳細說明如何根據明確指引來達成此義務，以協助我們發揮問 # 開發小組的最佳效能。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="0d5e2-114">作業和函式</span><span class="sxs-lookup"><span data-stu-id="0d5e2-114">Operations and Functions</span></span> ###

<span data-ttu-id="0d5e2-115">名稱應該建立的第一件事，就是指定的符號是否代表函式或作業。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="0d5e2-116">函式和作業之間的差異，對於瞭解程式碼區塊的行為非常重要。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="0d5e2-117">若要將函式和作業之間的區別傳達給使用者，我們需要使用副作用來處理該問答模組的配量作業。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="0d5e2-118">也就是說，作業*會執行*某些動作。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="0d5e2-119">相反地，函數會描述資料之間的數學關聯性。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="0d5e2-120">運算式 `Sin(PI() / 2.0)` 為 `1.0`，而*不*表示程式或其 qubits 的狀態。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="0d5e2-121">總結而言，作業會在函式的情況下執行工作。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="0d5e2-122">這種區別意味著我們將作業命名為動詞和函式做為名詞。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="0d5e2-123">當宣告使用者定義型別時，會同時隱含地定義用來建立該型別之實例的新函數。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="0d5e2-124">從該觀點來看，使用者定義型別應該命名為名詞，讓類型本身和函式函數具有一致的名稱。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="0d5e2-125">在合理的情況下，請確定作業名稱的開頭為動詞，以清楚指出作業所採取的效果。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="0d5e2-126">例如：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="0d5e2-127">有一個值得特別提及的案例，就是當作業接受另一個作業做為輸入並呼叫它時。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="0d5e2-128">在這種情況下，當定義外部作業時，輸入作業所採取的動作並不明確，因此不會立即清除正確的動詞。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="0d5e2-129">我們建議動詞 `Apply`，如同 `ApplyIf`、`ApplyToEach`和 `ApplyToFirst`。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="0d5e2-130">在此情況下，其他動詞也可能很有用，如同 `IterateThroughCartesianPower`。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="0d5e2-131">指令動詞</span><span class="sxs-lookup"><span data-stu-id="0d5e2-131">Verb</span></span> | <span data-ttu-id="0d5e2-132">預期的效果</span><span class="sxs-lookup"><span data-stu-id="0d5e2-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="0d5e2-133">套用</span><span class="sxs-lookup"><span data-stu-id="0d5e2-133">Apply</span></span> | <span data-ttu-id="0d5e2-134">提供做為輸入的作業稱為</span><span class="sxs-lookup"><span data-stu-id="0d5e2-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="0d5e2-135">判斷提示</span><span class="sxs-lookup"><span data-stu-id="0d5e2-135">Assert</span></span> | <span data-ttu-id="0d5e2-136">模擬器會檢查可能的量子測量結果的假設</span><span class="sxs-lookup"><span data-stu-id="0d5e2-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="0d5e2-137">Estimate</span><span class="sxs-lookup"><span data-stu-id="0d5e2-137">Estimate</span></span> | <span data-ttu-id="0d5e2-138">傳回的是傳統值，代表從一個或多個度量所繪製的估計</span><span class="sxs-lookup"><span data-stu-id="0d5e2-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="0d5e2-139">Measure</span><span class="sxs-lookup"><span data-stu-id="0d5e2-139">Measure</span></span> | <span data-ttu-id="0d5e2-140">會執行量子測量，並將其結果傳回給使用者</span><span class="sxs-lookup"><span data-stu-id="0d5e2-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="0d5e2-141">準備</span><span class="sxs-lookup"><span data-stu-id="0d5e2-141">Prepare</span></span> | <span data-ttu-id="0d5e2-142">Qubits 的給定暫存器會初始化為特定狀態</span><span class="sxs-lookup"><span data-stu-id="0d5e2-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="0d5e2-143">範例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-143">Sample</span></span> | <span data-ttu-id="0d5e2-144">從某個分佈隨機傳回的傳統值</span><span class="sxs-lookup"><span data-stu-id="0d5e2-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="0d5e2-145">針對函式，我們建議避免使用動詞來取代常用名詞（請參閱以下有關名詞的指引）或形容詞：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="0d5e2-146">特別的是，在幾乎所有情況下，我們建議使用過去的 participles，適當地指出函式名稱是強式連接到配量程式中其他位置的動作或副作用。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="0d5e2-147">例如，`ControlledOnInt` 使用動詞 "control" 的部分分詞形式，表示該函式做為修改其引數的形容詞。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="0d5e2-148">此名稱具有與內建 `Controlled` 仿函數的語義相符的額外優點，如下所述。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="0d5e2-149">同樣地，_代理程式名詞_也可以用來從作業名稱中建立函式和 UDT 名稱，例如，名稱 `Encoder` 用於與 `Encode`強烈相關聯的 udt。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0d5e2-150">指引</span><span class="sxs-lookup"><span data-stu-id="0d5e2-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0d5e2-151">我們建議：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-151">We suggest:</span></span>

- <span data-ttu-id="0d5e2-152">使用動詞做為作業名稱。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="0d5e2-153">使用名詞或形容詞作為函數名稱。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="0d5e2-154">針對使用者定義的類型和屬性使用名詞。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="0d5e2-155">針對所有可呼叫的名稱，請使用強式喜好設定中的 `CamelCase` 來 `pascalCase`、`snake_case`或 `ANGRY_CASE`。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="0d5e2-156">特別的是，請確定可呼叫的名稱是以大寫字母開頭。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="0d5e2-157">針對所有區域變數，請使用強式喜好設定中的 `pascalCase`，以 `CamelCase`、`snake_case`或 `ANGRY_CASE`。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="0d5e2-158">特別的是，請確定本機變數是以小寫字母開頭。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="0d5e2-159">避免在函式和作業名稱中使用底線 `_`;需要額外層級的階層時，請使用命名空間和命名空間別名。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0d5e2-160">範例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-160">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="0d5e2-161">名稱</span><span class="sxs-lookup"><span data-stu-id="0d5e2-161">Name</span></span> | <span data-ttu-id="0d5e2-162">說明</span><span class="sxs-lookup"><span data-stu-id="0d5e2-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="0d5e2-163">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="0d5e2-164">清除使用動詞（「反映」）來表示作業的效果。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="0d5e2-165">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="0d5e2-166">使用名詞片語建議函式，而不是運算。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="0d5e2-167">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="0d5e2-168">使用 `snake_case` contravenes Q # 標記法。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="0d5e2-169">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="0d5e2-170">使用底線 internal to operation name contravenes Q # 標記法。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="0d5e2-171">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="0d5e2-172">使用名詞片語會建議函式傳回作業。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="0d5e2-173">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="0d5e2-174">清除使用名詞（"事實"）來表示這是函式，而是形容詞。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="0d5e2-175">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="0d5e2-176">使用動詞（"get"）表示這是一項作業。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="0d5e2-177">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="0d5e2-178">使用名詞片語清楚地指的是呼叫 UDT 函數的結果。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="0d5e2-179">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="0d5e2-180">使用動詞命令時，建議 UDT 的函數是作業。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="0d5e2-181">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="0d5e2-182">使用名詞片語會傳達屬性的使用。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="0d5e2-183">速記和縮寫</span><span class="sxs-lookup"><span data-stu-id="0d5e2-183">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="0d5e2-184">前述的建議是，有許多形式的速記，會看到在量子運算中常見且普遍使用的用法。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-184">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="0d5e2-185">我們建議您在存在的現有和通用速記位置使用它，特別是針對目的電腦作業內建的作業。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-185">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="0d5e2-186">例如，我們選擇 `X` 的名稱，而不是 `ApplyX`，而是 `Rz`，而不是 `RotateAboutZ`。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-186">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="0d5e2-187">使用這類速記時，作業名稱應全部大寫（例如： `MAJ`）。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-187">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="0d5e2-188">在常用的縮寫和前列縮寫定義（例如 "QFT" 用於「量子傅立葉轉換」）中套用此慣例時，一定要特別注意。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-188">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="0d5e2-189">我們建議遵循一般的 .NET 慣例，以使用完整名稱中的縮寫和前列縮寫定義，這規定：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-189">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="0d5e2-190">兩個字母的縮寫和前列縮寫定義會以大寫（例如： "big endian" 的 `BE`）來命名，</span><span class="sxs-lookup"><span data-stu-id="0d5e2-190">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="0d5e2-191">所有較長的縮略字和前列縮寫定義都是以 `CamelCase` 命名（例如：「量子傅立葉轉換」的 `Qft`）</span><span class="sxs-lookup"><span data-stu-id="0d5e2-191">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="0d5e2-192">因此，執行 QFT 的作業可以 `QFT` 為速記來呼叫，或當做 `ApplyQft`寫出。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-192">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="0d5e2-193">對於特別常用的作業和函式，可能會想要提供縮寫名稱作為較長格式的_別名_：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-193">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0d5e2-194">指引</span><span class="sxs-lookup"><span data-stu-id="0d5e2-194">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0d5e2-195">我們建議：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-195">We suggest:</span></span>

- <span data-ttu-id="0d5e2-196">適當時，請考慮常用的已接受和廣泛使用的簡短名稱。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-196">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="0d5e2-197">針對速記使用大寫。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-197">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="0d5e2-198">使用大寫表示簡短（兩個字母）的縮寫和前列縮寫定義。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-198">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="0d5e2-199">使用 `CamelCase` 較長（三個或更多個字母）的縮寫和前列縮寫定義。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-199">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0d5e2-200">範例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-200">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="0d5e2-201">名稱</span><span class="sxs-lookup"><span data-stu-id="0d5e2-201">Name</span></span> | <span data-ttu-id="0d5e2-202">說明</span><span class="sxs-lookup"><span data-stu-id="0d5e2-202">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="0d5e2-203">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-203">☑</span></span> | `X` | <span data-ttu-id="0d5e2-204">適用于「套用 $X $ 轉換」的清楚縮寫</span><span class="sxs-lookup"><span data-stu-id="0d5e2-204">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="0d5e2-205">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-205">☑</span></span> | `CNOT` | <span data-ttu-id="0d5e2-206">「受控制-不」的易懂速記</span><span class="sxs-lookup"><span data-stu-id="0d5e2-206">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="0d5e2-207">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-207">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="0d5e2-208">速記不應在 `CamelCase`中。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-208">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="0d5e2-209">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-209">☑</span></span> | `ApplyQft` | <span data-ttu-id="0d5e2-210">Common initialism "QFT" 會顯示為完整格式名稱的一部分。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-210">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="0d5e2-211">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-211">☑</span></span> | `QFT` | <span data-ttu-id="0d5e2-212">Common initialism "QFT" 會顯示為縮寫名稱的一部分。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-212">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="0d5e2-213">名稱中有適當名詞</span><span class="sxs-lookup"><span data-stu-id="0d5e2-213">Proper Nouns in Names</span></span> ###

<span data-ttu-id="0d5e2-214">雖然在物理上，通常會在第一次發佈相關專案之後進行命名，但大部分的非 physicists 並不熟悉每個人的姓名和所有歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-214">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="0d5e2-215">依賴物理的命名慣例可能會導致進入重大屏障，因為來自其他背景的使用者必須瞭解大量看似不透明的名稱，才能使用常見的作業和概念。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-215">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="0d5e2-216">因此，我們建議在任何合理的情況下，將描述概念的一般名詞都採用強式喜好設定，以適當的名詞描述概念的發行歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-216">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="0d5e2-217">在特定的範例中，單向控制的交換和雙向控制的非作業通常稱為學術文獻中的「Fredkin」和「Toffoli」作業，但在 Q # 中識別的主要是 `CSWAP` 和 `CCNOT`。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-217">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="0d5e2-218">在這兩種情況下，API 檔批註都會根據適當名詞和所有適當的引文來提供同義字名稱。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-218">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="0d5e2-219">這個喜好設定特別重要，因為一定要有一些適當名詞的使用方式，例如，問 # 遵循許多傳統語言所設定的傳統，並參考布林邏輯參照中的 `Bool` 型別，也就是在接受時加以命名。George Boole。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-219">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="0d5e2-220">類似的一些量子概念會以類似的方式命名，包括問答 # 語言內建的 `Pauli` 類型。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-220">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="0d5e2-221">藉由將適當名詞的使用方式降到最低，這種用法並不重要，我們會降低無法合理地避免適當名詞的影響。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-221">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0d5e2-222">指引</span><span class="sxs-lookup"><span data-stu-id="0d5e2-222">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="0d5e2-223">我們建議：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-223">We suggest:</span></span>

- <span data-ttu-id="0d5e2-224">避免在名稱中使用適當名詞。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-224">Avoid the use of proper nouns in names.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0d5e2-225">範例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-225">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="0d5e2-226">類型轉換</span><span class="sxs-lookup"><span data-stu-id="0d5e2-226">Type Conversions</span></span> ###

<span data-ttu-id="0d5e2-227">由於 Q # 是強式和 staticly 型別語言，因此一種類型的值只能使用類型轉換函式的明確呼叫，當做另一個類型的值使用。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-227">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="0d5e2-228">這與允許以隱含方式變更類型的語言（例如：類型升階）或透過轉換而成。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-228">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="0d5e2-229">因此，型別轉換函式在 Q # 程式庫開發中扮演著重要的角色，並包含其中一個常見的命名相關決策。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-229">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="0d5e2-230">不過，我們會注意到，因為型別轉換一律是_決定性_的，所以它們可以撰寫為函式，因此會落在上述建議之下。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-230">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="0d5e2-231">特別的是，我們建議類型轉換函式絕不能命名為動詞（例如： `ConvertToX`）或副詞介係詞片語（`ToX`），但應該命名為形容詞介係詞片語，以指出來源和目的地類型（`XAsY`).</span><span class="sxs-lookup"><span data-stu-id="0d5e2-231">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="0d5e2-232">在類型轉換函式名稱中列出陣列類型時，我們建議速記 `Arr`。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-232">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="0d5e2-233">避免發生例外狀況，我們建議您使用 `As` 來命名所有類型轉換函式，以便快速識別這些函數。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-233">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0d5e2-234">指引</span><span class="sxs-lookup"><span data-stu-id="0d5e2-234">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0d5e2-235">我們建議：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-235">We suggest:</span></span>

- <span data-ttu-id="0d5e2-236">如果函式將類型的值 `X` 轉換成 `Y`類型的值，請使用 `AsY` 或 `XAsY`的名稱。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-236">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0d5e2-237">範例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-237">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="0d5e2-238">名稱</span><span class="sxs-lookup"><span data-stu-id="0d5e2-238">Name</span></span> | <span data-ttu-id="0d5e2-239">說明</span><span class="sxs-lookup"><span data-stu-id="0d5e2-239">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="0d5e2-240">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-240">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="0d5e2-241">介係詞 "to" 會產生動詞片語，表示作業，而不是函數。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-241">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="0d5e2-242">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-242">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="0d5e2-243">輸入類型不會從函式名稱中清除。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-243">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="0d5e2-244">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-244">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="0d5e2-245">輸入和輸出類型以錯誤的順序出現。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-245">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="0d5e2-246">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-246">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="0d5e2-247">輸入類型和輸出類型都是明確的。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-247">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="0d5e2-248">私用或內部名稱</span><span class="sxs-lookup"><span data-stu-id="0d5e2-248">Private or Internal Names</span></span> ###

<span data-ttu-id="0d5e2-249">在許多情況下，名稱僅適用于程式庫或專案的內部使用，而且不是程式庫所提供之 API 的保證部分。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-249">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="0d5e2-250">明確指出在命名函式和作業時，這是很有説明的，讓僅限內部程式碼的意外相依性變得顯而易見。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-250">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="0d5e2-251">如果作業或函式不適合直接使用，而是應該由部分應用程式所使用的相符可呼叫來使用，請考慮針對部分套用的可呼叫使用開頭為 `_` 的名稱。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-251">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0d5e2-252">指引</span><span class="sxs-lookup"><span data-stu-id="0d5e2-252">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0d5e2-253">我們建議：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-253">We suggest:</span></span>

- <span data-ttu-id="0d5e2-254">當函式、作業或使用者定義型別不屬於 Q # 程式庫或程式的公用 API 時，請確定其名稱開頭為前置底線（`_`）。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-254">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0d5e2-255">範例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-255">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="0d5e2-256">名稱</span><span class="sxs-lookup"><span data-stu-id="0d5e2-256">Name</span></span> | <span data-ttu-id="0d5e2-257">說明</span><span class="sxs-lookup"><span data-stu-id="0d5e2-257">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="0d5e2-258">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-258">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="0d5e2-259">底線 `_` 不應出現在名稱的結尾。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-259">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="0d5e2-260">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-260">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="0d5e2-261">開頭的底線 `_` 清楚地指出此作業僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-261">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="0d5e2-262">變體</span><span class="sxs-lookup"><span data-stu-id="0d5e2-262">Variants</span></span> ###

<span data-ttu-id="0d5e2-263">雖然這項限制可能不會在未來的 Q # 版本中持續存在，但目前還是通常會有一組相關的作業或函式，這些群組會根據其輸入支援的函子，或其引數的具體類型來區分。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-263">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="0d5e2-264">這些群組可以使用相同的根名稱，後面接著一或兩個表示其 variant 的字母來加以區別。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-264">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="0d5e2-265">尾碼</span><span class="sxs-lookup"><span data-stu-id="0d5e2-265">Suffix</span></span> | <span data-ttu-id="0d5e2-266">意義</span><span class="sxs-lookup"><span data-stu-id="0d5e2-266">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="0d5e2-267">預期支援 `Adjoint` 的輸入</span><span class="sxs-lookup"><span data-stu-id="0d5e2-267">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="0d5e2-268">預期支援 `Controlled` 的輸入</span><span class="sxs-lookup"><span data-stu-id="0d5e2-268">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="0d5e2-269">預期支援 `Controlled` 和 `Adjoint` 的輸入</span><span class="sxs-lookup"><span data-stu-id="0d5e2-269">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="0d5e2-270">輸入或輸入的類型為 `Int`</span><span class="sxs-lookup"><span data-stu-id="0d5e2-270">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="0d5e2-271">輸入或輸入的類型為 `Double`</span><span class="sxs-lookup"><span data-stu-id="0d5e2-271">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="0d5e2-272">輸入或輸入的類型為 `BigInt`</span><span class="sxs-lookup"><span data-stu-id="0d5e2-272">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0d5e2-273">指引</span><span class="sxs-lookup"><span data-stu-id="0d5e2-273">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0d5e2-274">我們建議：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-274">We suggest:</span></span>

- <span data-ttu-id="0d5e2-275">如果函式或作業與其輸入的型別和仿函數支援無關，則不會使用尾碼。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-275">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="0d5e2-276">如果函式或作業是由其輸入的型別和仿函數支援所關聯的任何類似函式或運算，請使用上表中的尾碼來區別變體。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-276">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0d5e2-277">範例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-277">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="0d5e2-278">引數和變數</span><span class="sxs-lookup"><span data-stu-id="0d5e2-278">Arguments and Variables</span></span> ###

<span data-ttu-id="0d5e2-279">函式或作業的 Q # 程式碼的主要目標，是為了方便閱讀和瞭解。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-279">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="0d5e2-280">同樣地，輸入和類型引數的名稱應該會傳達函式或引數在提供後的使用方式。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-280">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidancetabguidance"></a>[<span data-ttu-id="0d5e2-281">指引</span><span class="sxs-lookup"><span data-stu-id="0d5e2-281">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0d5e2-282">我們建議：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-282">We suggest:</span></span>

- <span data-ttu-id="0d5e2-283">針對所有變數和輸入名稱，請使用強式喜好設定中的 `pascalCase`，以 `CamelCase`、`snake_case`或 `ANGRY_CASE`。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-283">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="0d5e2-284">輸入名稱應該是描述性的;盡可能避免一或兩個字母名稱。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-284">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="0d5e2-285">只接受一個型別引數的作業和函式應該會在其角色很明顯時，以 `T` 表示該型別引數。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-285">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="0d5e2-286">如果函式或作業接受多個型別引數，或單一型別引數的角色不明顯，請考慮針對每個型別使用開頭為 `T` 的簡短大寫字組（例如： `TOutput`）。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-286">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="0d5e2-287">不包含引數和變數名稱中的類型名稱;這項資訊可以和應該由您的開發環境提供。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-287">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="0d5e2-288">依其常值名稱（`flagQubit`）和陣列類型（以複數（`measResults`））表示純量類型。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-288">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="0d5e2-289">對於 qubits 的陣列而言，請考慮以 `Register` 表示這類類型，其中的名稱指的是以某種方式緊密相關的 qubits 序列。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-289">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="0d5e2-290">當做陣列索引使用的變數應該以 `idx` 開頭，而且應該是單數的（例如： `things[idxThing]`）。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-290">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="0d5e2-291">特別是，強烈避免使用單字母變數名稱做為索引;請考慮至少使用 `idx`。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-291">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="0d5e2-292">用來保存陣列長度的變數應該以 `n` 開頭，而且應該是複數化（例如： `nThings`）。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-292">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0d5e2-293">範例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-293">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="0d5e2-294">使用者定義型別名稱專案</span><span class="sxs-lookup"><span data-stu-id="0d5e2-294">User Defined Type Named Items</span></span> ###

<span data-ttu-id="0d5e2-295">使用者定義類型中的命名專案應該命名為 `CamelCase`，即使在 UDT 的輸入中也一樣。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-295">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="0d5e2-296">這有助於在使用存取子標記法（例如： `callable::Apply`）或複製和更新標記法（`set arr w/= Data <- newData`）時，清楚地將命名的專案與本機範圍變數的參考區隔開。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-296">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0d5e2-297">指引</span><span class="sxs-lookup"><span data-stu-id="0d5e2-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0d5e2-298">我們建議：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-298">We suggest:</span></span>

- <span data-ttu-id="0d5e2-299">UDT 函式中的命名專案應該命名為 `CamelCase`;也就是說，它們應該以初始大寫開頭。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-299">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="0d5e2-300">解析為作業的命名專案應該命名為動詞階段。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-300">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="0d5e2-301">未解析為作業的命名專案應該命名為名詞片語。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-301">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="0d5e2-302">對於包裝作業的 Udt，應定義名為 `Apply` 的單一名為的專案。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-302">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0d5e2-303">範例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-303">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="0d5e2-304">片段</span><span class="sxs-lookup"><span data-stu-id="0d5e2-304">Snippet</span></span> | <span data-ttu-id="0d5e2-305">說明</span><span class="sxs-lookup"><span data-stu-id="0d5e2-305">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="0d5e2-306">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-306">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="0d5e2-307">`Apply` 的名稱是 `CamelCase`格式的動詞片語，以建議已命名的專案是一項作業。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-307">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="0d5e2-308">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-308">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="0d5e2-309">命名專案的開頭必須是初始大寫字母。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-309">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="0d5e2-310">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-310">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="0d5e2-311">解析為函式的命名專案應該命名為名詞片語，而不是動詞片語。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-311">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="0d5e2-312">輸入慣例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-312">Input Conventions</span></span> ##

<span data-ttu-id="0d5e2-313">當開發人員呼叫作業或函式時，必須以特定順序指定該作業或函數的各種輸入，進而增加開發人員所面臨的認知負載，以便使用程式庫。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-313">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="0d5e2-314">特別是，記住輸入排序的工作通常是來自手邊工作的干擾：程式設計配量演算法。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-314">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="0d5e2-315">雖然豐富的 IDE 支援可以減輕這種情況，但良好的設計和遵循一般慣例也有助於將 API 所施加的認知負載降到最低。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-315">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="0d5e2-316">可能的話，減少作業或函式所預期的輸入數目會很有説明，因此，每個輸入的角色對於呼叫該作業或函式的開發人員，以及稍後閱讀該程式碼的開發人員而言，會更容易察覺。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-316">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="0d5e2-317">特別是當您無法或合理地減少作業或函式的引數數目時，一定要具有一致的順序，以將使用者在預測輸入順序時所面臨的驚訝降到最低。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-317">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="0d5e2-318">我們建議輸入排序慣例，其主要衍生自將部分應用程式視為 currying f （x，y）≡ f （x）（y）的一般化。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-318">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="0d5e2-319">因此，部分套用第一個引數應該會產生可呼叫的，這在合理的情況下會非常有用。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-319">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="0d5e2-320">遵循此原則，請考慮使用下列引數順序：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-320">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="0d5e2-321">傳統不可呼叫的引數，例如角度、冪向量等等。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-321">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="0d5e2-322">可呼叫的引數（函數和引數）。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-322">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="0d5e2-323">如果函式和作業都做為引數，請考慮將作業放在函數之後。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-323">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="0d5e2-324">藉由可呼叫引數來處理的集合，其方式類似于 `Map`、`Iter`、`Enumerate`和 `Fold`。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-324">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="0d5e2-325">當做控制項使用的 Qubit 引數。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-325">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="0d5e2-326">當做目標使用的 Qubit 引數。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-326">Qubit arguments used as targets.</span></span>

<span data-ttu-id="0d5e2-327">假設有一個作業 `ApplyPhaseEstimationIteration` 在採用角度和 oracle 的階段估計中使用，將角度傳遞至由不同縮放比例的陣列所修改的 `Rz`，然後控制 oracle 的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-327">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="0d5e2-328">我們會以下列方式排序輸入 `ApplyPhaseEstimationIteration`：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-328">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
<span data-ttu-id="0d5e2-329">以最少驚訝的特殊案例而言，某些函數和作業會模擬內建函子 `Adjoint` 和 `Controlled`的行為。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-329">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="0d5e2-330">例如，`ControlledOnInt<'T>` 具有類型 `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`，因此 `ControlledOnInt<Qubit[]>(5, _)` 的作用就像 `Controlled` 仿函數，但在控制項暫存器代表 state $ \ket{5} = \ket{101}$ 的條件上。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-330">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="0d5e2-331">因此，開發人員預期 `ControlledOnInt` 的輸入會放上最後轉換的可呼叫，而產生的作業會採用作為其輸入 `(Qubit[], 'T)`---與 `Controlled` 仿函數輸出相同的順序。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-331">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0d5e2-332">指引</span><span class="sxs-lookup"><span data-stu-id="0d5e2-332">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0d5e2-333">我們建議：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-333">We suggest:</span></span>

- <span data-ttu-id="0d5e2-334">使用與部分應用程式一致的輸入排序。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-334">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="0d5e2-335">使用與內建函子一致的輸入排序。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-335">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="0d5e2-336">將所有的傳統輸入放在任何量子輸入之前。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-336">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0d5e2-337">範例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-337">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="0d5e2-338">檔慣例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-338">Documentation Conventions</span></span> ##

<span data-ttu-id="0d5e2-339">Q # 語言可讓您透過使用特殊格式的檔批註，將檔附加至作業、函式和使用者定義類型。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-339">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="0d5e2-340">以三斜線（`///`）表示，這些檔批註是小型[DocFX-Flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)檔，可用來描述每個作業、函式和使用者定義類型的用途、每個預期的輸入等等。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-340">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="0d5e2-341">配量開發工具組所提供的編譯器會將這些批註解壓縮，並使用它們來協助排版類似于 https://docs.microsoft.com/quantum的檔。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-341">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="0d5e2-342">同樣地，隨配量開發工具組提供的語言伺服器會使用這些批註，在使用者將滑鼠停留在其 Q # 程式碼的符號上方時提供協助。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-342">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="0d5e2-343">藉由使用檔批註，可以讓使用者瞭解程式碼，方法是提供有用的參考，以取得使用本檔中的其他慣例無法輕鬆表示的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-343">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="0d5e2-344">
    [檔批註語法參考](xref:microsoft.quantum.language.statements#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="0d5e2-344">
    [Documentation comment syntax reference](xref:microsoft.quantum.language.statements#documentation-comments)
</span></span></div>

<span data-ttu-id="0d5e2-345">若要有效地使用此功能來協助使用者，建議您在撰寫檔批註時記住一些事項。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-345">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0d5e2-346">指引</span><span class="sxs-lookup"><span data-stu-id="0d5e2-346">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="0d5e2-347">我們建議：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-347">We suggest:</span></span>

- <span data-ttu-id="0d5e2-348">每個公用函式、作業和使用者定義型別都應該緊接在檔批註前面。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-348">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="0d5e2-349">每個檔批註至少應該包含下列區段：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-349">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="0d5e2-350">摘要</span><span class="sxs-lookup"><span data-stu-id="0d5e2-350">Summary</span></span>
    - <span data-ttu-id="0d5e2-351">輸入</span><span class="sxs-lookup"><span data-stu-id="0d5e2-351">Input</span></span>
    - <span data-ttu-id="0d5e2-352">輸出（如果適用）</span><span class="sxs-lookup"><span data-stu-id="0d5e2-352">Output (if applicable)</span></span>
- <span data-ttu-id="0d5e2-353">請確定所有摘要都是兩個句子或更少。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-353">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="0d5e2-354">如果需要更多空間，請在 `# Summary` 後立即提供 `# Description` 區段，其中包含完整的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-354">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="0d5e2-355">在合理的情況下，請勿在摘要中包含數學運算，因為並非所有用戶端都支援摘要中的 TeX 標記法。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-355">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="0d5e2-356">請注意，撰寫 prose 檔（例如 TeX 或 Markdown）時，最好使用較長的行長度。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-356">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="0d5e2-357">在 [`# Description`] 區段中提供所有相關的數學運算式。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-357">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="0d5e2-358">在描述輸入時，請勿重複每個輸入的類型，因為它們可以由編譯器推斷，而風險會造成不一致的情況。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-358">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="0d5e2-359">提供適當的範例，每個都在自己的 `# Example` 區段中。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-359">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="0d5e2-360">在列出程式碼之前，請先簡短地描述每個範例。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-360">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="0d5e2-361">在 `# References` 區段中提及所有相關的學術刊物（例如：論文、訴訟、blog 文章和替代的執行），做為連結的項目符號清單。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-361">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="0d5e2-362">請確定在可能的情況下，所有引文連結都是永久和固定識別碼（DOIs 或已建立版本的 arXiv 號碼）。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-362">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="0d5e2-363">當作業或函式透過仿函數變體與其他作業或函數相關時，請在 `# See Also` 區段中，將其他變體列為專案符號。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-363">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="0d5e2-364">在層級1（`/// #`）區段之間保留空白的批註行，但不要在層級2（`/// ##`）區段之間留下空白的一行。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-364">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0d5e2-365">範例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-365">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="0d5e2-366">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-366">☑</span></span> ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a><span data-ttu-id="0d5e2-367">格式設定慣例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-367">Formatting Conventions</span></span> ##

<span data-ttu-id="0d5e2-368">除了上述的建議之外，也有助於讓程式碼盡可能清楚，以使用一致的格式化規則。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-368">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="0d5e2-369">根據本質，這類格式規則通常是任意的，而且相當於個人美學。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-369">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="0d5e2-370">儘管如此，我們建議您在共同作業者群組中維護一組一致的格式設定慣例，特別是針對大型 Q # 專案（例如，量子開發工具組本身）。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-370">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="0d5e2-371">這些規則可以使用與 Q # 編譯器整合的格式工具自動套用。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-371">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="0d5e2-372">指引</span><span class="sxs-lookup"><span data-stu-id="0d5e2-372">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="0d5e2-373">我們建議：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-373">We suggest:</span></span>

- <span data-ttu-id="0d5e2-374">使用四個空格，而不是可攜性的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-374">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="0d5e2-375">例如，在 VS Code：</span><span class="sxs-lookup"><span data-stu-id="0d5e2-375">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="0d5e2-376">行在合理的79個字元。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-376">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="0d5e2-377">在二元運算子前後使用空格。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-377">Use spaces around binary operators.</span></span>
- <span data-ttu-id="0d5e2-378">在用於類型注釋的冒號兩邊使用空格。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-378">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="0d5e2-379">在陣列和元組常值中使用逗號後面加上一個空格（例如，在函數和作業的輸入中）。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-379">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="0d5e2-380">請勿在函數、作業或 UDT 名稱之後，或在屬性宣告中 `@` 之後使用空格。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-380">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="0d5e2-381">每個屬性宣告都應該在自己的行上。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-381">Each attribute declaration should be on its own line.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="0d5e2-382">範例</span><span class="sxs-lookup"><span data-stu-id="0d5e2-382">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="0d5e2-383">片段</span><span class="sxs-lookup"><span data-stu-id="0d5e2-383">Snippet</span></span> | <span data-ttu-id="0d5e2-384">說明</span><span class="sxs-lookup"><span data-stu-id="0d5e2-384">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="0d5e2-385">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-385">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="0d5e2-386">在二元運算子前後使用空格。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-386">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="0d5e2-387">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-387">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="0d5e2-388">在類型批註冒號前後使用空格。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-388">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="0d5e2-389">☑</span><span class="sxs-lookup"><span data-stu-id="0d5e2-389">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="0d5e2-390">輸入元組中的專案會正確地分隔，以方便閱讀。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-390">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="0d5e2-391">☒</span><span class="sxs-lookup"><span data-stu-id="0d5e2-391">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="0d5e2-392">在函數、作業或 UDT 名稱之後，應該隱藏空格。</span><span class="sxs-lookup"><span data-stu-id="0d5e2-392">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***

