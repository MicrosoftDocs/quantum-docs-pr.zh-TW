---
title: '進一步瞭解-Q # 技術 |Microsoft Docs'
description: '進一步瞭解-Q # 技術'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: bd2b799d4001e280baccb04158247891b9cbb5bc
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820193"
---
# <a name="going-further"></a><span data-ttu-id="e4ae1-103">進一步瞭解</span><span class="sxs-lookup"><span data-stu-id="e4ae1-103">Going Further</span></span> #

<span data-ttu-id="e4ae1-104">既然您已瞭解如何在 Q # 中撰寫有趣的配量程式，本節將進一步介紹一些更先進的主題，以供未來使用。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>


## <a name="generic-operations-and-functions"></a><span data-ttu-id="e4ae1-105">一般作業和函數</span><span class="sxs-lookup"><span data-stu-id="e4ae1-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="e4ae1-106">本節假設您對[中C#的泛型](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics) [、 F#中的泛型、](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/) [ C++範本](https://docs.microsoft.com/cpp/cpp/templates-cpp)或類似的方法，對其他語言的元人員有基本的熟悉程度。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="e4ae1-107">我們可能會想要定義的許多函式和作業實際上並不會依賴其輸入的類型，而只會透過一些其他函式或運算，隱含地使用其類型。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="e4ae1-108">例如，請考慮許多功能性語言通用的*地圖*概念;假設函式 $f （x） $ 和值 $\{的集合 x_1，x_2，\dots ..，x_n\}$，map 會傳回新的集合 $\{f （x_1），f （x_2），\dots ..，f （x_n）\}$。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="e4ae1-109">若要在 Q # 中執行此功能，我們可以利用該函式是第一個類別。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="e4ae1-110">讓我們寫出 `Map`的快速範例，使用★作為預留位置，同時瞭解我們所需的類型。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="e4ae1-111">請注意，無論我們在什麼實際的型別中，此函式看起來都很相似。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="e4ae1-112">例如，從整數到 Paulis 的對應，與從浮點數到字串的對應大致相同：</span><span class="sxs-lookup"><span data-stu-id="e4ae1-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="e4ae1-113">在原則上，我們可以針對我們所遇到的每一對類型撰寫 `Map` 版本，但這會造成一些問題。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="e4ae1-114">比方說，如果我們在 `Map`中發現錯誤，則必須確保在所有 `Map`版本上一致地套用修正程式。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="e4ae1-115">此外，如果我們要建立新的元組或 UDT，則現在也必須建立新的 `Map` 來與新的型別搭配使用。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="e4ae1-116">雖然這是少數這類函式的方便追蹤，但我們會收集與 `Map`相同形式的多個函式，而引入新類型的成本會以相當短的順序過長為大。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="e4ae1-117">不過，大部分的困難之處在于，我們並未提供編譯器所需的資訊來辨識不同版本的 `Map` 相關聯的方式。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="e4ae1-118">實際上，我們希望編譯器將 `Map` 視為某種數學函式，從 Q # 型別*到 q* # 函數。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="e4ae1-119">這種概念的正規化方式是讓函式和作業具有*型別參數*，以及它們的一般元組參數。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="e4ae1-120">在上述範例中，我們想要將 `Map` 視為 `Int, Pauli` 第一個案例中的型別參數，並在第二個案例中 `Double, String`。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="e4ae1-121">在大部分的情況下，這些類型參數可以用來當做一般類型使用：我們會使用類型參數的值來建立陣列和元組、呼叫函數和作業，以及指派給一般或可變變數。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="e4ae1-122">間接相依性最極端的情況，就是 qubits，其中 Q # 程式無法直接依賴 `Qubit` 類型的結構，但**必須**將這類類型傳遞給其他作業和函式。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="e4ae1-123">回到上述範例，我們可以看到我們需要 `Map` 具有型別參數，一個用來表示 `fn` 的輸入，另一個則代表 `fn`的輸出。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="e4ae1-124">在 Q # 中，這是藉由在其宣告中的函式或作業名稱後面加上角括弧（也就是 `<>`，而不是 brakets $ \braket{}$！）來撰寫，並列出每個類型參數。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="e4ae1-125">每個型別參數的名稱都必須以 tick `'`開頭，表示它是型別參數，而不是一般型別（也稱為*具體*型別）。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="e4ae1-126">針對 `Map`，我們會撰寫：</span><span class="sxs-lookup"><span data-stu-id="e4ae1-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="e4ae1-127">請注意，`Map<'Input, 'Output>` 的定義看起來非常類似于之前寫出的版本。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="e4ae1-128">唯一的差別在於，我們明確通知編譯器，`Map` 不會直接相依于 `'Input` 和 `'Output`，但可透過 `fn`間接使用來處理任何兩種類型。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="e4ae1-129">一旦以這種方式定義 `Map<'Input, 'Output>` 之後，就可以像一般函式一樣呼叫它：</span><span class="sxs-lookup"><span data-stu-id="e4ae1-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="e4ae1-130">撰寫泛型函式和作業是一個位置，其中「元組元組輸出」是一種非常有用的方法，可以思考問 # 函式和作業。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="e4ae1-131">由於每個函式都只接受一個輸入，而且只會傳回一個輸出，因此類型的輸入 `'T -> 'U` 會符合*任何*Q # 函數。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="e4ae1-132">同樣地，任何作業都可以傳遞至 `'T => 'U`類型的輸入。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="e4ae1-133">作為第二個範例，請考慮撰寫會傳回兩個其他函式之組合的函式的挑戰：</span><span class="sxs-lookup"><span data-stu-id="e4ae1-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="e4ae1-134">在這裡，我們必須確切指定 `A`、`B`和 `C` 的內容，因此會嚴重限制新的 `Compose` 函數的公用程式。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="e4ae1-135">畢竟，`Compose` 只取決於 `A`、`B`，以及透過 `innerFn`*和 `outerFn`的 `C`。*</span><span class="sxs-lookup"><span data-stu-id="e4ae1-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="e4ae1-136">或者，我們可以將型別參數新增至 `Compose`，表示它適用于*任何*`A`、`B`和 `C`，只要這些參數符合 `innerFn` 和 `outerFn`所預期的參數即可：</span><span class="sxs-lookup"><span data-stu-id="e4ae1-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="e4ae1-137">Q # 標準程式庫提供了這類類型參數化作業和函式的範圍，讓您更容易表達更高順序的控制流程。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="e4ae1-138">這些會在[問答 # 標準程式庫指南](xref:microsoft.quantum.libraries.standard.intro)中進一步討論。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="e4ae1-139">借用 Qubits</span><span class="sxs-lookup"><span data-stu-id="e4ae1-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="e4ae1-140">「借款」機制可讓您配置 qubits，在計算期間用來做為臨時空間。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="e4ae1-141">這些 qubits 通常不是處於乾淨狀態，也就是說，它們不一定會在已知狀態中初始化，例如 $ \ket{0}$。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="e4ae1-142">其中一個人也說「中途」 qubits，因為其狀態不明，甚至可以與量子電腦記憶體的其他部分光子。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="e4ae1-143">在已變更 qubits 的已知使用案例中，是多個受控制 CNOT-CONTAINS 閘道的實作為，只需要極少的 qubits 和 incrementers。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="e4ae1-144">在 canon 中，有使用 `borrowing` 關鍵字的範例，例如，`MultiControlledXBorrow` 定義的函數。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="e4ae1-145">如果 `controls` 代表應該加入 `X` 作業中的控制項 qubits，則這個執行會新增 `Length(controls)-2` 許多中途 ancillas 的整體。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

<span data-ttu-id="e4ae1-146">請注意，`With` 結合---的廣泛使用，其格式適用于支援 adjoint 的作業，也就是在此範例中進行 `WithA`---，這是很好的程式設計風格，因為將控制項加入至包含 `With` 的結構只會將控制項傳播至內部作業。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="e4ae1-147">此外，請注意，除了作業的 `body` 之外，也會明確提供作業的 `controlled` 主體的執行，而不是使用 `controlled auto` 的語句。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="e4ae1-148">這是因為我們從線路的結構得知如何輕鬆加入進一步的控制項，相較于將控制項新增至 `body`中的每個個別閘道。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="e4ae1-149">將此程式碼與另一個 canon 函式進行比較有其意義 `MultiControlledXClean` 這種方式可達到相同的目標來執行乘法控制的 `X` 作業，不過，它會使用 `using` 機制的幾個乾淨 qubits。</span><span class="sxs-lookup"><span data-stu-id="e4ae1-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 
