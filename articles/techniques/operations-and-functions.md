---
title: '作業和函數-Q # 技術 |Microsoft Docs'
description: '作業和函數-Q # 技術'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fca20bb44cc42008f7d25d2fc71a39b962525c2
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820771"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="6b1c7-103">Q # 作業和函數</span><span class="sxs-lookup"><span data-stu-id="6b1c7-103">Q# Operations and Functions</span></span>

<span data-ttu-id="6b1c7-104">Q # 程式是由一或多個*作業*所組成，其中描述配量作業可以對量子資料進行的副作用，以及一或多個允許修改傳統資料的*函數*。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="6b1c7-105">相對於作業，函數是用來描述純粹的傳統行為，而且除了計算傳統輸出值之外，也不會有任何影響。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="6b1c7-106">在 Q # 中定義的每個作業都可以呼叫任何數目的其他作業，包括語言所定義的內建內建函式作業。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="6b1c7-107">定義這些內部作業的特定方式取決於目的電腦。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="6b1c7-108">在編譯時，每個作業都會表示為可提供給目的電腦的 .NET 類別類型。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="6b1c7-109">定義新的作業</span><span class="sxs-lookup"><span data-stu-id="6b1c7-109">Defining New Operations</span></span>

<span data-ttu-id="6b1c7-110">如上所述，以 Q # 撰寫之配量程式最基本的建立區塊是作業，可以從傳統 .NET 應用程式*呼叫，例如*，使用模擬器，或由 Q # 內的其他作業呼叫。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="6b1c7-111">每個作業都會接受輸入、產生輸出，並指定一或多個作業特製化的執行。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="6b1c7-112">例如，下列作業只會定義預設的本文特製化，並以單一 qubit 作為其輸入，然後在該輸入上呼叫內建的 `X` 作業：</span><span class="sxs-lookup"><span data-stu-id="6b1c7-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="6b1c7-113">關鍵字 `operation` 會開始作業定義，後面接著名稱。在這裡，`BitFlip`。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="6b1c7-114">接下來，輸入的型別會定義為 `Qubit`，以及用來參考新作業內輸入的名稱 `target`。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="6b1c7-115">同樣地，`Unit` 會定義作業的輸出是空的。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="6b1c7-116">這種用法類似于C#和其他命令式語言中的 `void`，而且相當於和其他F#功能性語言中的 `unit`。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="6b1c7-117">下面將更詳細地探討此問題，但每個 Q # 中的作業只會接受一個輸入，並只傳回一個輸出。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="6b1c7-118">接著會使用*元組*來表示多個輸入和輸出，這會將多個值一起收集成單一值。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="6b1c7-119">非正式地說，問 # 是一種「元組輸出」語言。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="6b1c7-120">遵循此概念之後，`()` 應該會讀取為「空的」元組，其類型 `Unit`。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="6b1c7-121">在新作業中，如果只需要明確指定預設本文特殊化的執行，就可以在宣告中直接指定實值。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="6b1c7-122">此外，您也可以定義的執行，例如一或多個 `functor` 作業，如下所述。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="6b1c7-123">在上述範例中，唯一的語句是呼叫內建的 Q # 作業 <xref:microsoft.quantum.intrinsic.x>。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="6b1c7-124">作業也會傳回比 `Unit`更有趣的類型。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="6b1c7-125">例如，<xref:microsoft.quantum.intrinsic.m> 作業會傳回 `Result`類型的輸出，表示已執行測量。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="6b1c7-126">我們可以將作業的輸出傳遞至另一個作業，或可以搭配 `let` 關鍵字來定義新的變數。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="6b1c7-127">這可代表在較低層級與量子作業互動的傳統計算，例如 superdense 編碼：</span><span class="sxs-lookup"><span data-stu-id="6b1c7-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="6b1c7-128">函子、adjoint 和控制</span><span class="sxs-lookup"><span data-stu-id="6b1c7-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="6b1c7-129">如果作業會執行單一轉換，則可以定義作業在*adjointed*或*控制*時的運作方式。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="6b1c7-130">作業的 adjoint 特製化會指定它在反向執行時的運作方式，而受控制的特製化則會指定作業在配量暫存器的狀態下套用時的運作方式。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="6b1c7-131">這些特製化的存在可以宣告為作業簽章的一部分：在下列範例中 `is Adj + Ctl`。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="6b1c7-132">然後編譯器會產生每個這類隱含宣告特製化的對應執行。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="6b1c7-133">Q # 中的許多作業都代表單一閘道。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="6b1c7-134">如果 $U $ 是由作業 `U`表示的單一閘道，則 `Adjoint U` 代表單一閘道 $U ^ \dagger $。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="6b1c7-135">如果編譯器無法產生執行，則可以明確指定。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="6b1c7-136">這類明確特製化宣告可以包含適當的世代指示詞或使用者定義的實作為。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="6b1c7-137">範例中 `PrepareEntangledPair` 的程式碼相當於下列程式碼，其中包含明確的特製化宣告：</span><span class="sxs-lookup"><span data-stu-id="6b1c7-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="6b1c7-138">關鍵字 `auto` 表示編譯器應該決定如何產生特製化執行。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="6b1c7-139">如果編譯器無法自動產生特定特製化的實作為，或者可以指定更有效率的執行，則也可以手動定義執行。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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
<span data-ttu-id="6b1c7-140">在上述範例中，`adjoint invert;` 指出 adjoint 特製化是藉由將主體實作為反轉而產生，`controlled adjoint invert;` 表示會藉由反轉受控制特製化的指定實作為來產生受控制的 adjoint 特製化。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="6b1c7-141">我們會在[更高順序的控制流程](xref:microsoft.quantum.concepts.control-flow)中看到更多的範例。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="6b1c7-142">若要呼叫作業的特製化，請使用 `Adjoint` 或 `Controlled` 關鍵字。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="6b1c7-143">例如，您可以使用 adjoint `PrepareEntangledPair` 將光子狀態轉換回 unentangled 組 qubits，以撰寫更簡潔地的上述 superdense 程式碼範例：</span><span class="sxs-lookup"><span data-stu-id="6b1c7-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="6b1c7-144">設計要與函子搭配使用的作業時，有一些重要的限制需要考慮。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="6b1c7-145">最重要的是，使用任何其他作業的輸出值之作業的特製化，不能由編譯器自動產生，因為在這類作業中重新排序語句以取得相同的效果並不明確。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="6b1c7-146">定義新函數</span><span class="sxs-lookup"><span data-stu-id="6b1c7-146">Defining New Functions</span></span>

<span data-ttu-id="6b1c7-147">問 # 也允許定義函式，這與作業*不同，因為*它們不允許超出計算輸出值的任何效果。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="6b1c7-148">特別是，函式無法呼叫作業、對 qubits 採取動作、取樣亂數，或以其他方式相依于函式的輸入值以外的狀態。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="6b1c7-149">因此，Q # 函式是*單純*的，因為它們一律會將相同的輸入值對應到相同的輸出值。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="6b1c7-150">這可讓 Q # 編譯器在產生作業特製化時，安全地重新排序呼叫函式的方式和時機。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="6b1c7-151">定義函式的運作方式類似于定義作業，不同之處在于無法為函式定義任何 adjoint 或受控特殊化。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="6b1c7-152">例如：</span><span class="sxs-lookup"><span data-stu-id="6b1c7-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="6b1c7-153">只要能夠這麼做，就能以函式而非作業的形式寫出傳統邏輯，這會很有説明，可以更輕鬆地從作業中使用。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="6b1c7-154">例如，如果我們以作業撰寫 `Square`，則編譯器無法保證以相同的輸入呼叫它會一致地產生相同的輸出。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="6b1c7-155">若要以底線表示函式和作業之間的差異，請考慮傳統方式從 Q # 操作中取樣亂數字的問題：</span><span class="sxs-lookup"><span data-stu-id="6b1c7-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="6b1c7-156">每次呼叫 `U` 時，它在 `target`上會有不同的動作。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="6b1c7-157">特別的是，編譯器無法保證如果我們將 `adjoint auto` 特製化宣告加入 `U`，`U(target); Adjoint U(target);` 會做為身分識別（也就是不需要 op）。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="6b1c7-158">這會違反我們在[向量和矩陣](xref:microsoft.quantum.concepts.vectors)中看到的 adjoint 定義，讓能夠在我們呼叫作業的作業中自動產生 adjoint 特製化，<xref:microsoft.quantum.math.randomreal> 會中斷編譯器所提供的保證;<xref:microsoft.quantum.math.randomreal> 是不存在 adjoint 或控制版本的作業。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="6b1c7-159">另一方面，允許 `Square` 之類的函式呼叫是安全的，因為編譯器可以確保它只需要保留 `Square` 的輸入，才能保持其輸出穩定。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="6b1c7-160">因此，將盡可能多的傳統邏輯隔離到函式，可讓您輕鬆地在其他函數和作業中重複使用該邏輯。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="6b1c7-161">控制流程</span><span class="sxs-lookup"><span data-stu-id="6b1c7-161">Control Flow</span></span>

<span data-ttu-id="6b1c7-162">在作業或函式內，每個語句會依序執行，類似于最常見的命令式傳統語言。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="6b1c7-163">不過，您可以透過三種不同的方式修改這個控制流程：</span><span class="sxs-lookup"><span data-stu-id="6b1c7-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="6b1c7-164">`if` 語句</span><span class="sxs-lookup"><span data-stu-id="6b1c7-164">`if` Statements</span></span>
- <span data-ttu-id="6b1c7-165">`for` 迴圈</span><span class="sxs-lookup"><span data-stu-id="6b1c7-165">`for` Loops</span></span>
- <span data-ttu-id="6b1c7-166">`repeat`-`until` 迴圈</span><span class="sxs-lookup"><span data-stu-id="6b1c7-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="6b1c7-167">我們會在討論[重複直到成功（ru）](xref:microsoft.quantum.techniques.qubits#measurements)線路之前，延遲對後者的討論。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="6b1c7-168">不過，`if` 和 `for` 控制流程結構，對於大部分的傳統程式設計語言而言，都是以熟悉的方式進行。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="6b1c7-169">特別是，`if` 語句可以接受條件，後面可能接著一個或多個 `elif` 語句，而且可能以 `else`結尾：</span><span class="sxs-lookup"><span data-stu-id="6b1c7-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

<span data-ttu-id="6b1c7-170">同樣地，`for` 迴圈表示在整數範圍或陣列元素上的反復專案：</span><span class="sxs-lookup"><span data-stu-id="6b1c7-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="6b1c7-171">重要的是，`for` 迴圈和 `if` 語句甚至可以用於自動產生特殊化的作業中。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="6b1c7-172">在此情況下，`for` 迴圈的 adjoint 會反轉方向，並接受每個反復專案的 adjoint。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="6b1c7-173">這會遵循「鞋與 socks」原則：如果您想要復原並加上「鞋」，您必須先復原鞋，然後再復原「socks」。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="6b1c7-174">如果您還在戴鞋，也能讓您更輕鬆地嘗試並將您的 socks 轉成由於！</span><span class="sxs-lookup"><span data-stu-id="6b1c7-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="6b1c7-175">作為第一級值的作業和函式</span><span class="sxs-lookup"><span data-stu-id="6b1c7-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="6b1c7-176">使用函式而不是作業來推理控制流程和傳統邏輯的一項重要技巧，就是利用 Q # 中的作業和函*式是第一類*。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="6b1c7-177">也就是說，它們是語言中的每個值本身的許可權。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="6b1c7-178">例如，下列是完全有效的 Q # 程式碼，如果有一點間接：</span><span class="sxs-lookup"><span data-stu-id="6b1c7-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="6b1c7-179">上述程式碼片段中的變數 `ourH` 值就是作業 <xref:microsoft.quantum.intrinsic.h>，因此我們可以像任何其他作業一樣呼叫該值。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="6b1c7-180">這可讓我們撰寫在其輸入過程中採取作業的作業，形成更高順序的控制流程概念。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="6b1c7-181">比方說，我們可以想像一下，將作業套用到相同的目標 qubit 兩次，以「正方形」作業。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="6b1c7-182">在此範例中，出現在類型 `(Qubit => Unit)` 中的 `=>` 箭號表示輸入欄位 `op` 是做為其輸入類型 `Qubit` 的作業，並產生空的元組做為其輸出。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="6b1c7-183">此外，我們還指定該作業類型的特性，其中包含支援哪些函子的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="6b1c7-184">`(Qubit => Unit)` 類型的作業不支援 `Adjoint` 或 `Controlled` 仿函數。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="6b1c7-185">如果我們想要指出該類型的作業必須支援（例如 `Adjoint` 仿函數），我們必須將它宣告為 adjointable。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="6b1c7-186">這是藉由使用注釋 `is Adj` 至類型來完成。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="6b1c7-187">同樣地，`(Qubit => Unit is Ctl)` 表示該類型的作業支援 `Controlled` 仿函數。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="6b1c7-188">我們將在討論 [Q # 中的類型] （x： microsoft 量子. 類型模型）時進一步探討。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-188">We will explore this further when we discuss [types in Q#] (xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="6b1c7-189">現在，我們強調，我們也可以將作業當做輸出的一部分傳回，讓我們可以將一些傳統條件式邏輯隔離為傳統函式，以作業的形式傳回量副程式的描述。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="6b1c7-190">做為簡單的範例，請考慮 teleportation 範例，其中接收兩個傳統訊息的合作物件需要使用訊息，將其 qubit 解碼為適當的傳送狀態。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="6b1c7-191">我們可以根據採用這兩個傳統位的函式撰寫此程式，並傳回適當的解碼作業。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="6b1c7-192">這個新函式確實是一個函式，在此情況下，如果我們使用相同的 `hereBit` 和 `thereBit`值來呼叫它，我們一律會取回相同的作業。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="6b1c7-193">因此，可以安全地在作業內執行此解碼器，而不需考慮解碼邏輯如何與不同作業特製化的定義互動。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="6b1c7-194">也就是，我們已將傳統邏輯隔離在函式內，並保證編譯器，只要保留輸入，函式呼叫就可以與 impunity 重新排序。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="6b1c7-195">我們也可以將函式視為第一類的值，因為我們會在討論[作業和](#operations-and-functions-as-first-class-values)函式類型時更詳細地看到。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="6b1c7-196">部分套用作業和函式</span><span class="sxs-lookup"><span data-stu-id="6b1c7-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="6b1c7-197">我們可以透過使用*部分應用程式*來傳回作業的函式執行更多動作，我們可以將輸入的一個或多個部分提供給函式或作業，而不需要實際呼叫它。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="6b1c7-198">例如，若要重新叫用上述的 `ApplyTwice` 範例，我們可以指出我們不想要對應套用輸入作業的 qubit 指定：</span><span class="sxs-lookup"><span data-stu-id="6b1c7-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="6b1c7-199">在此情況下，本機變數 `twiceOp` 保留部分套用的作業 `ApplyTwice(op, _)`，其中尚未指定的輸入部分會以 `_`表示。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="6b1c7-200">當我們實際在下一行呼叫 `twiceOp` 時，我們會將輸入的所有剩餘部分當做原始作業傳遞給部分套用的作業。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="6b1c7-201">因此，上述程式碼片段與直接呼叫 `ApplyTwice(op, target)` 相同，因此我們引進了新的區域變數，讓我們能夠延遲呼叫，同時提供輸入的某些部分。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="6b1c7-202">由於已部分套用的作業並不會實際被呼叫，直到提供了完整的輸入為止，我們也可以安全地從函式內部分套用作業。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="6b1c7-203">就原則而言，`SquareOperation` 中的傳統邏輯可能更牽涉到，但它仍會與作業的其餘部分隔離，因為編譯器可以提供關於函數的保證。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="6b1c7-204">這種方法會在整個 Q # 標準程式庫中用來以可在量副程式中輕鬆使用的方式來表示傳統控制流程。</span><span class="sxs-lookup"><span data-stu-id="6b1c7-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>
